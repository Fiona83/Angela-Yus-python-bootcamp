# Angela-Yus-python-bootcampe 
This repository contains the projects I did based on Angela Yu's 100 Days of python bootcamp. 

The projects are done on Replit and since I haven't found a way to link multiple Replit repls into one Github Repository, I just put links here, so that you can click the links and than read the codes or even fork the repl.

**_Since I tried my best to work through the projects alone without watch the solution first. The code here might not be very same as Angela's final code. You can cross check my codes and Angela's to see which one you prefer._**

## Useful tools
1. Free tools to draw flowcharts

https://app.diagrams.net/

This tool can draw online and save the charts on your harddisc. It also has a desktop version which you can download.

2. Online code visualization / debugger

[pythontutor.com](https://pythontutor.com/)

Just paste your code into the website and click next. It simulates a debugging process and visualize the input and output of the code. It is very helpful to understand hwo the code runs and to debug the code.

3. ASCII Art Generator

http://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20

This online small tool helps you to generate ASCII Art to be used as logo for your program.

4. Open Trivia Database

https://opentdb.com/

This website is a free open source database for commen questions. You can use its api to generate a list of questions and use it for your code.

5. RGB Tool from w3school

https://www.w3schools.com/colors/colors_rgb.asp

This online tool can help you to check the color with RGB values.

6. Color Hunt

https://colorhunt.co/

This is a very nice website with a database of beautiful colors. The colors are presented in HEX value which can be very easy to use in the code.

7. Latitude and Longtitude Finder

https://www.latlong.net/

On this website you can give a name of the city and it will return you the latitude and longtitude of your location. You can also pin on the map to get your latitude and longtitude.

8. Sunset and Sunrise times API

https://sunrise-sunset.org/api

This API can give you the time of sunrise and sunset according your latitude and longtitude.


## Projects
### Level: Beginner

Day 7 Hangman Game

https://replit.com/@Fiona83/Day-7-Hangman-final

Day 8 Caesar Cipher Program

https://replit.com/@Fiona83/Day-8-caesar-cipher-final

Day 9 Blind Auction

https://replit.com/@Fiona83/Day-9-blind-auction-final

Day 10 Calculator

https://replit.com/@Fiona83/Day-10-calculator-final#main.py

Day 11 Blackjack Game

https://replit.com/@Fiona83/Day-11-blackjack-final

Day 12 Guess the Number Game

https://replit.com/@Fiona83/Day-12-guess-the-number-final

Day 14 Higher Lower Game

https://replit.com/@Fiona83/Day-14-higher-lower-final

Day 15 Coffee Machine

https://replit.com/@Fiona83/Day-15-coffee-machine-final

### Level: Intermediate

Day 16 OOP Coffee Machine

https://replit.com/@Fiona83/Day-16-oop-coffee-machine-final

Day 17 The Quiz Project

https://replit.com/@Fiona83/Day-17-quiz-game-final

Day 18 The Hirst Painting

https://replit.com/@Fiona83/Day-18-the-hirst-painting-final

Day 19 Turtle Race

https://replit.com/@Fiona83/Day-19-turtle-race-final

Day 20 Snake Game

https://replit.com/@Fiona83/Day-20-snake-game

Day 23 Turtle Crossing

https://replit.com/@Fiona83/Day-23-turtle-crossing-final


Day 24 Mail Merge

https://replit.com/@Fiona83/Day-24-mail-merge-final

Day 25 US States Game

https://replit.com/@Fiona83/Day-25-us-states-final

Day 26 NATO Alphabet

https://replit.com/@Fiona83/Day-26-NATO-alphabet-final

Day 28 Pomodoro

https://replit.com/@Fiona83/Day-28-Pomodoro-final

> For this project, I added more funktions to the promodoro such as pause the timer and resume it. Angela's solution didn't check some of the corner case such as if the user click the start button more than once. The original version has bug in this case.

Day 29 Password Manager

https://replit.com/@Fiona83/Day-29-password-manager

> By Day 30, the project is upgraded to store and read data in json and add exception handling.

Day 31 Flash Card Project

https://replit.com/@Fiona83/Day-31-flash-card-project-final

> In this project, I managed to fix the bug which Angela didn't mention. When we keep on removing words from the list, evantually till some point, we have learned all the words and the list becomes empty. Then the whole click right button, remove words from the list etc will cause a bunch of bugs. In my version, this bug is handled. I provide a short version of csv file with only 5 words so that you can test the project with it. After learning all the words, instead of showing the next card which does not exist, my version will give you a congratulation message. And very important, the to_learn_file.csv will be deleted from the folder. An empty csv file will cause the program to crash when you next time run it.

Day 32 Birthday Wisher

https://replit.com/@Fiona83/Day-32-birthday-wisher-final#birthdays.csv

> In this project, I haven't used Angela's approach to create the dictionary like {(month, day): data_row}. Because this approach has one problem. If we have more than one person with the same birthday, it will only give you the last one in the csv file. Dictionary cannot have two identical keys. My version is able to send birthday emails to more than one person when they have the same birthday.

Day 33 Kanye Quotes

https://replit.com/@Fiona83/Day-33-kanye-quotes-final

Day 33 ISS Overhead

https://replit.com/@Fiona83/Day-33-issoverhead-final

Day 34 Quizzler App

https://replit.com/@Fiona83/Day-34-quizzler-app-final

Day 35 Rain Alert

https://replit.com/@Fiona83/Day-35-rain-alert-final

> For this project, instead of sending SMS I used Email as an alert. Because I don't want to sign up a bounch of account.

> While doing this project, I was really struggling with the environment variables. When I used export in my terminal, the variable will be created temporary. When I closed my terminal window, the variables are gone. Then I have to googled a little bit and ended up writing export command in my .bash_profile file. After that, the variables are permenant set. However when I ran my code in pycharm or in terminal windows within Atom, they both returned None for my variables. After long digging, I finally found out that both pycharm and Atom have to be restarted after the variable been set, so that they can get the values from the system. So if you are also struggling with the environment varialbles, remember to restart your pycharm. 

> Here is a document with different ways to import environment variables into a python project. You might want to check it if you do not want to mess up the system file. [Using Environment Variables in Python](./Using_Environment_Variable_in_Python.md)

Day 36 Stock News

https://replit.com/@Fiona83/Day-36-stock-news-final

> For this project, also using Email instead of sending SMS. Interesting thing is the normal sendmail function in smtp library is not able to treat unicode. If you have unicode letters which is out of the range of ASCII, you will get a traceback. In order to solve this problem, I used email library to encode the message, so that the sendmail function can handle the unicode letters and emojis in the mail.



