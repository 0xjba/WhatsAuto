---
name: 'WhatsAuto'
description: 'Automate sending Whatsapp messages using Python'
author: '@the-injineer'
---
How easy it would have been if sending messages
WhatsAuto is a program that uses pywhatkit which is a Python library for automating WhatsApp to send messages like daily quotes, news, market news, etc. 

![](img/final-demo.png)

In this workshop, you’re going to create a Python program to automate sending Whatsapp messages, in less than 5 lines of code.

## 🚀 Getting started

We’re going to be using [pywhatkit](https://pypi.org/project/pywhatkit/), a Python library for automation to make this project. This project also a Web Browser most preferably Chrome, to access Whatsapp web webpage.

Install the Pywhatkit library using the pip function in python.
```
pip install pywhatkit
```
Awesome! Now that we’ve installed pywhatkit, we’re ready to import the library to setup the environment.

## 💻 Setting up the Project

Create a Directory for the project; Example: WhatsAuto
Inside the Project directory create the python program for automation.
```
import pywhatkit
```
Great! Now that we’ve imported pywhatkit, we are all good with the automation part.

So lets send some messages.

```
pywhatkit.sendwhatmsg("+919*********","Hello, Buddy",15,00)
```
Just put the recievers phone number followed by the message & finally the time to send the message.

NOTE:
