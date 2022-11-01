# Using Environment Variables in Python

As we begin to sending Emails or using APIs with authorizations, we need to code our password or API keys in our code. However it is not very safe to just hard code the password or private keys in the code, especially when we want to upload our code to the public repositories. In this case, we can use environment variables. Those variables are stored locally.

In this documentation, I will introduce three different ways to use einvironment variables. 

## 1. Export Environment Variables in Terminal

The easiest way to define a environment variable is to use **export** command. As shown in the graphic below, we export a variable called "TEST_VAR" and then we can use it in python environment.

![Export Variable in Terminal](images/terminal_export_env_1.png)

The problem here is we cannot access the variable in Atom or in Pycharm. 

![Variable not accessable in Atom](images/terminal_export_env_2.png)

And if we close the terminal window and restart a new terminal, the variable is gone.

![Variable disappear after restart](images/terminal_export_env_3.png)

In order to solve this problem, we can export the variable permanantly into system file.

## 2. Export Environment Variables into the System File


