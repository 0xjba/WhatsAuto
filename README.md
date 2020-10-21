---
name: 'WhatsAuto'
description: 'Automate sending Whatsapp messages using Python'
author: '@the-injineer'
---
How easy it would have been if sending important daily messages automatically & in a scheduled manner was possible. Lets make that MAGIC happen.
WhatsAuto is a program that uses pywhatkit which is a Python library for automating WhatsApp to send messages like daily quotes, news, market news, etc. 

![](img/final-demo.png)

In this workshop, you’re going to create a Python program to automate sending Whatsapp messages, in less than 15 lines of code.

## 😇 Prerequisites
You should have a beginner understanding of:
Python
JSON

If you dont have a idea about this, then dont worry this workshop will give you the bare essentials to get started.

## 🚀 Getting started

We’re going to be using [pywhatkit](https://pypi.org/project/pywhatkit/), a Python library for automation to make this project. This project also requires a Web Browser most preferably Chrome, to access Whatsapp web webpage.

Install the Pywhatkit library using the pip function in python.
What is pip?-[pip](https://docs.python.org/3/installing/index.html) is a de facto standard package-management system used to install and manage software packages written in Python.
```
pip install pywhatkit
```

## 💻 Setting up the Pywhatkit Module.

Awesome! Now that we’ve installed pywhatkit, we’re ready to [import](https://docs.python.org/3/reference/import.html
) the library to setup the environment, but before that lets create a Directory for the project; Example: WhatsAuto.

Inside the Project directory create the file for python program, then import the module.
```
import pywhatkit
```
Great! Now that we’ve imported pywhatkit, we are all good with the automation part.

Just put the recievers phone number followed by the message & finally the time to send the message.
```
pywhatkit.sendwhatmsg("+919*********","Hello World",15,00)
```
NOTE:Pywhatkit doesnt accept Time with preciding zeroes.

## 💾 Obtaining the data to be shared.
Large amount of data of many services like Weather, Traffic & a lot more can be accessed with their API's. We will be using here API's( application programming interface) which throws out data in [JSON](https://www.json.org/json-en.html) form. But before that what exactly is a API, it is a set of functions that allows applications to access data and interact with external software components, operating systems, or microservices.

To obtain data from an API we need to import the JSON & [requests](https://requests.readthedocs.io/en/master/api/) module.
```
import json
import requests
```
Using the GET function we will request for the data from the API & will store it in a variable.
```
quotedata = requests.get("http://quotes.stormconsultancy.co.uk/random.json")
```
JSON data obtained from the API has multiple data stored in a key-value pair.
Example:
```
{"author":"Mark Gibbs","id":36,"quote":"No matter how slick the demo is in rehearsal, when you do it in front of a live audience, the probability of a flawless presentation is inversely proportional to the number of people watching, raised to the power of the amount of money involved.","permalink":"http://quotes.stormconsultancy.co.uk/quotes/36"}
```
We need to extract the specific data from the JSON data obtained & store it in a variable.
```
quote = quotedata.json()['quote']
```
