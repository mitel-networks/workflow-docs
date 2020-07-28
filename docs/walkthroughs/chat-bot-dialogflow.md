---
layout: default
title: Building a chat bot with Dialogflow
parent: Walkthroughs
nav_order: 1
---

Dialogflow is a natural language understanding platform from Google that makes it easy to design and integrate a conversational user interfaces such as chatbots. Using works flow we can add a chatbot to a CloudLink chat conversation.

## Setup Google integration
Setup the integration to Google by following the instruction found here:
<https://mitel-networks.github.io/workflow-docs/docs/integrations/google/>
The scopes required for Dialogflow are https://www.googleapis.com/auth/cloud-platform and https://www.googleapis.com/auth/dialogflow
More details can be found here: <https://developers.google.com/identity/protocols/oauth2/scopes#dialogflow>

## Create chatbot as platform user
To be a participant in the conversation the chatbot needs to be created as a CloudLink platform user. Using the accounts portal (<https://accounts.mitel.io>) create a user for the chatbot. 

## Clone the Dialogflow example
There is an example of a flow that can be used to handle an interaction with the chatbot in the recipes section. To get started you can clone that recipe which is called "Dialogflow Interaction Example".

![](../../../assets/walkthroughs/clone-recipe.gif)

## Configure the flow
The cloned flow requires some extra configuration. 

1 *Set the Google integration connection on the Dialogflow activity*

2 *Set the flow to run as the chatbot identity*

## Start a conversation with the chatbot
From an application that uses CloudLink chat such as MiCollab start a conversation with the chatbot.
