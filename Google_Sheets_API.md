# How to use Google Sheets API

First of all, please read the [Python Quickstart](https://developers.google.com/sheets/api/quickstart/python) of Google Sheets API. The whole setting of Google Sheet API is a little bit comlicated.

## Preparation
1. Install the google package for python

```
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

2. [create a Google Cloud Project](https://console.cloud.google.com/projectcreate)

Just give some project name to it and click create.

3. Enable Google Workspace API

From the sidebar choose **"APIs & Services" -> "Enable APIs and Services"**. Then you can search **"Google Sheets API"** and enable it.

4. Create Credentials

Then from the sidebar choose **"APIs & Services" -> "Credentials"**. Here I didn't follow the [Python Quickstart](https://developers.google.com/sheets/api/quickstart/python), but a video from YouTube. Maybe later I will try the "OAuth 2.0 Client IDs" to see how it works. Here I choose **"+ CREATE CREDENTIALS"** and then choose **"Service Account"**. Then just choose some name and ID. It then create a email address as the account and generate a json file for your project. You should later put this json file into your project folder. Or if you prefer to save it somewhere else give the absolute path in your code, so that your credential canbe generated using this file.

5. Share your Google Sheet with this Service Account

The next step is share the google sheet you want to access with this newly created service account. Just visit your google sheet and on the top right side click **"Share"** and then add the email address of the service account into it. The type can be **"Editor"** so that it can read and write the sheet.

## Using API in Python Code
