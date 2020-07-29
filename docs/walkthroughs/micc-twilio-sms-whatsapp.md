---
layout: default
title: MiCC B with Twilio SMS or Whatsapp messaging
parent: Walkthroughs
nav_order: 1
---

## Setup Twilio integration

## Configure MiCC integration
To route the incoming messaging interaction from Twilio we need to clone the provided recipe called "Twilio MiCC Recipe" which can be found under Library -> Recipes. Click clone the clone button and a flow will be created from this recipe.

![](../../../assets/walkthroughs/clone-recipe.gif)

Once the flow is cloned we need to select the integration connection to be used for the outgoing messages. This is done by clicking on the trigger and selecting the integration setup in the earlier step.

![](../../../assets/walkthroughs/choose-connection.gif)

In order to link to MiCC we need to add a tag to the Workflow. This tag is specific to MiCC and is used by MiCC to identify this flow. The tag to be added is "MiCCB-768736b3-5485-4ac2-8a6e-05e1712a9802"

![](../../../assets/walkthroughs/add-micc-tag.gif)

Once this tag is added if you close and reopen the flow you will see that the flow is updated to run as a specific identity. This identity is the CloudLink ClientId used by the CloudLink Proxy running on the MiCC server. 

![](../../../assets/walkthroughs/workflow-identity.png)

This completes the setup of the flow

## Configure Twilio with webhook URL
Now the flow is setup this is ready to receive POST requests from Twilio when there is an incoming message. 
First step is to get the webhook URL for the flow that was just created. To do this click on the run button in the top right and hit the button to copy the URL to the clipboard. 

![](../../../assets/walkthroughs/get-webhook-url.gif)

## Ready
The setup is now complete, incoming messages recieved from Twilio will be routed into the connected MiCC. 

## Use a specific MiCC queue
If these interactions should be routed to a specific MiCC queue rather than the main inbound flow then you can configure the MiCC queue identity on the flow. Click on the trigger and set the default value of the QueueId variable to the MiCC queue ID. 

![](../../../assets/walkthroughs/select-micc-queue.gif)
