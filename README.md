---
name: 'WhatsAuto'
description: 'Automate sending Whatsapp messages using Python'
author: '@the_injineer'
---

WhatsAuto is a program that uses pywhatkit which is a Python library for automating WhatsApp to send messages. 

![](img/final-demo.png)

In this workshop, you’re going to create a Python program to automate sending Whatsapp messages, in less than 5 lines of code.

## Getting started

We’re going to be using [pywhatkit](https://pypi.org/project/pywhatkit/), a Python library for automation to make this project. This project also requires Chrome Browser or [Chomedriver.exe](https://chromedriver.chromium.org/) to access Whatsapp web webpage.

Install the Pywhatkit library using the pip function in python.
```
pip install pywhatkit
```
Awesome! Now that we’ve installed pywhatkit, we’re ready to import the library to setup the environment.

## Setting up the Project

Create a Directory for the project; Example: WhatsAuto
Inside the Project directory create the python program for automation.
```
import pywhatkit as kit
```
Great! Now that we’ve imported pywhatkit, we’re ready to start setting up the whatsapp web for automation.

Now Mention the path to Chromedriver.exe or Chrome browser.
```
kit.add_driver_path('chromedriver.exe')
```
Easiest way is to use the Chromedriver.exe & place it in the project directory itself.

Now, lets setup the Whatsapp using Whatsapp Web. 
```
kit.load_QRcode()
```
This loads the Whatsapp web page to scan the QR code & access your Whatsapp from desktop.

Hooray! We are done with the setup for automation, so lets send some messages.

```
pywhatkit.sendwhatmsg("+919*********","Hello, Buddy",15,00)
```
Just put the recievers phone number followed by the message & finally the time to send the message.

NOTE:
