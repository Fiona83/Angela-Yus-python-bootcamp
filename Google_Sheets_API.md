# How to use Google Sheets API

First of all, please read the [Python Quickstart](https://developers.google.com/sheets/api/quickstart/python) of Google Sheets API. The whole setting of Google Sheet API is a little bit comlicated.

## Preparation
1. Install the google package for python

```
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

2. [Create a Google Cloud Project](https://console.cloud.google.com/projectcreate)

Just give some project name to it and click create.

3. Enable Google Workspace API

From the sidebar choose **"APIs & Services" -> "Enable APIs and Services"**. Then you can search **"Google Sheets API"** and enable it.

4. Create Credentials

Then from the sidebar choose **"APIs & Services" -> "Credentials"**. Here I didn't follow the [Python Quickstart](https://developers.google.com/sheets/api/quickstart/python), but a video from YouTube. Maybe later I will try the "OAuth 2.0 Client IDs" to see how it works. Here I choose **"+ CREATE CREDENTIALS"** and then choose **"Service Account"**. Then just choose some name and ID. It then create a email address as the account and generate a json file for your project. You should later put this json file into your project folder. Or if you prefer to save it somewhere else give the absolute path in your code, so that your credential canbe generated using this file.

5. Share your Google Sheet with this Service Account

The next step is share the google sheet you want to access with this newly created service account. Just visit your google sheet and on the top right side click **"Share"** and then add the email address of the service account into it. The type can be **"Editor"** so that it can read and write the sheet.

## Using API in Python Code
Now the preparation work is done and we can begin to read and write our google sheet. Below is am example of the python code from my flight alert project. 

```Python
from googleapiclient.discovery import build
from google.oauth2 import service_account

# create google sheets API credential
SERVICE_ACCOUNT_FILE = 'google_key.json' # Here should be your json file generated from google
SCOPES = ['https://www.googleapis.com/auth/spreadsheets']
CRED = service_account.Credentials.from_service_account_file(
    SERVICE_ACCOUNT_FILE, scopes=SCOPES)

# This is the ID of your sheet
SHEET_ID = '1rfkuamS80WAqySzzAuI2P_KftXLcA0jleSMecbmPrR0' 
# For Google API while reading or writing you shoul always define a data range. I will explain it later.
PRICE_RANGE_NAME = 'prices' 
USER_RANGE_NAME = "users"

# create connection with Sheets API
service = build('sheets', 'v4', credentials=CRED)
sheet_connect = service.spreadsheets()

# read data
result = sheet_connect.values().get(spreadsheetId=SHEET_ID,
                                    range=PRICE_RANGE_NAME).execute()
data_sheet = result.get('values', [])

# write data
sheet_connect.values().update(spreadsheetId=SHEET_ID,
                              range=PRICE_RANGE_NAME, valueInputOption="USER_ENTERED",
                              body={"values": data_sheet}).execute()

# append data
response = sheet_connect.values().append(spreadsheetId=SHEET_ID,
                                         range=USER_RANGE_NAME, valueInputOption="USER_ENTERED",
                                         body={"values": user_info}).execute()
print(f"{(response.get('updates').get('updatedCells'))} cells appended.")


```



