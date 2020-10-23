---
name: 'WhatsAuto'
description: 'Automate sending Whatsapp messages using Python'
author: '@the-injineer'
---
How easy it would have been if sending important daily messages automatically and in a scheduled manner was possible. Let's make that MAGIC happen.
WhatsAuto is a program that uses pywhatkit which is a Python library for automating WhatsApp to send messages 💬 like daily quotes, news, market news, etc. 

![](img/banner.png)

In this workshop, you’re going to create a Python program to automate sending Whatsapp messages, in less than 10 lines of code.

## 😇 Prerequisites

You should have a beginner understanding of Python & JSON.

If you don't have an idea about this, then don't worry this workshop will give you the bare essentials to get started.

## 🚀 Getting started

We’re going to be using [pywhatkit](https://pypi.org/project/pywhatkit/), a Python library for automation to make this project. This project also requires a Web Browser most preferably Chrome, to access Whatsapp web webpage.

Install the Pywhatkit library using the `pip` function in python.
What is pip?-[pip](https://docs.python.org/3/installing/index.html) is a de facto standard package-management system used to install and manage software packages written in Python.

```py
pip install pywhatkit
```

## 💻 Setting up the Pywhatkit Module.

Awesome! Now that we’ve installed pywhatkit, we’re ready to [import](https://docs.python.org/3/reference/import.html
) the library to set up the environment, but before that let's create a Directory for the project; Example: WhatsAuto.

Inside the Project directory create the file for the python program, then `import` the module.

```py
import pywhatkit
```

Great! Now that we’ve imported pywhatkit, we are all good with the automation part.

Just put the receiver's phone number followed by the message 💬 & finally the time to send the message 💬.

```py
pywhatkit.sendwhatmsg("+919*********","Hello World",15,00)

```
NOTE: pywhatkit doesnt accept Time with preciding zeroes.

## 🌐 Fetching Data

A Large amount of data of many services like Weather, Traffic & a lot more can be accessed with their APIs. We will be using here APIs( application programming interface) which throws out data in [JSON](https://www.json.org/json-en.html) form. But before that what exactly is a API, it is a set of functions that allows applications to access data and interact with external software components, operating systems, or microservices.

To obtain data from an API we need to import the JSON & [requests](https://requests.readthedocs.io/en/master/api/) module.

```py
import json
import requests

```
Using the `GET` function we will request for the data from the API & will store it in a variable.

```py
quotedata = requests.get("http://quotes.stormconsultancy.co.uk/random.json")

```
JSON data obtained from the API has multiple data stored in a key-value pair.

```
print(quotedata)
```

Try pasting this code in your [repl.it](https://repl.it) project, and your console should have Programming quotes in it 😛
Example:

```json
{"author":"Mark Gibbs","id":36,"quote":"No matter how slick the demo is in rehearsal, when you do it in front of a live audience, the probability of a flawless presentation is inversely proportional to the number of people watching, raised to the power of the amount of money involved.","permalink":"http://quotes.stormconsultancy.co.uk/quotes/36"}
```
We need to extract the specific data from the JSON data obtained & store it in a variable.

```py
quote = quotedata.json()['quote']
```

Pretty straight forward, right? 😄

## 🛠️ Putting it all together

To make our program, all we need to do is get the data from the API using `requests.get` function then send a message 💬 using the `pywhatkit` module.

```py
import requests
import json
import pywhatkit as kit
quotedata = requests.get("http://quotes.stormconsultancy.co.uk/random.json")
quote = quotedata.json()['quote']
phone = input("Enter a Mobile Number with country code in your Contacts to send a quote:")
print("Enter the Time to send message, at least 5 mins from the current time")
hour = int(input("Enter hour in 24hrs Format without preciding zeroes:"))
minutes = int(input("Enter minutes without preciding zeroes:"))
kit.sendwhatmsg(phone, quote ,hour, minutes)
```

The Data retrieved from the API is stored in Variables & then the `pywhatkit` module utilizes this data to send the messages 💬. 
Message 💬 can be sent through `pywhatkit` using `pywhatkit.sendwhatmsg("+919*********","Hello World",15,00)` command. But the module requires the end-user to manually code & enter the input data required for sending messages 💬, To avoid this we can store the data in a variable (phone, hour, & time) & ask from the end user making it easy to use the program. The necessary instructions for the user are given by printing the sentences using `print` function.
 
## ⚡ What's next?

Now that you know how to build & automate sending WhatsApp messages 💬, try sending messages 💬 to your friends and family, and also use different JSON APIs to send different information through Whatsapp. This Program can be developed in various ways & integrated with other services to make life easy. 

Here are some you can get your hands dirty with 👇

- [COVID API](https://covid19api.com/) (Share Daily COVID Case reports)
- [News API](https://newsapi.org/) (Share Latest & Trending News as Messages)
- [Weather API](https://openweathermap.org/api) (Share Up to date weather reports)
- [Stock Market API](https://finnhub.io/) (Up to date Stock & Crypto Market Data)
- [Football API](https://www.api-football.com/) (Live Scores or Highlights of all Football Matches)

Wanna Brainstorm more! Code for this program & different implementations is on my GitHub, feel free to fork, send amazing PRs to it ✨
