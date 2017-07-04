---
services: bots
platforms: nodejs
author: denniszielke
---

# Simple bot on azure with NodeJs
This sample shows you how to deploy a simple bot hosted on Azure Websites. 

![Simple Bot Hackathon](./images/architecture.png)

For a complete end-to-end walk-through of creating this application, please refer to the [Bot Builder SDK for Node.js](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-overview)

## Deploying this sample
1. Deploy the arm template in arm/template.json to azure

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdenniszielke%2Fhackbotsimple%2Fmaster%2Farm%2Ftemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>  

It will deploy the following resources
- Azure Web App
- Application Insights
- Code from github to the WebApp

## Register your bot with Microsoft
Go to https://dev.botframework.com/bots and create a new bot.
Give it a name and enter the application insights values from the initial resource deployment

## Prepare your blank azure vm for development

1. Open Internet Explorer (does not work on Chrome) and paste the following URL: 

http://boxstarter.org/package/nr/url?https://raw.githubusercontent.com/denniszielke/hackbotsimple/master/scboxstarter.txt

2. Click Run on the security warning. 
3. Click Run again when prompted. 
4. This will take about 5 minutes and does the setup of prerequired software: Visual Studio Code, NodeJs, Git, Google Chrome, Fiddler4

## Set the environment variables for local dev test
1. Download the bot framework emulator from https://emulator.botframework.com/ 
2. Create an .env file by renaming the .env_template file and fill in the variables from the arm template deployment output

## Run the bot locally
1. Run npm install to install the dependencies
2. Run the bot in debug mode in VSCode
3. Connect the bot emulator to your instance running on localhost (appid and apppassword have to be empty for localhost)