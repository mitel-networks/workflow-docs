---
layout: default
title: Sunshine Conversations
parent: Integrations
nav_order: 1
---

## Sunshine Conversations

Note the information below comes primarily from the third party vendor. Website links / wording and steps may change without notice. 

Connections to Sunshine Communcations are authenticated using HTTP Basic authentication. API keys are used to access the REST API. The API keys are composed of an id and a secret.

### Creating an App API Key
From the Sunshine Conversations dashboard, select your app and then select the settings tab. As you can see in the screenshot, the id and a secret are provided after creating an API Key.

![](../../../assets/integrations/sunshine_api_keys.png)

### Adding the integration in Workflow Studio
Under Library -> Integrations click "Add New" and select Sunshine Conversations. Once the integration is added click "Complete Setup" and enter the ID and SECRET from in the provided boxes. In the host box you will enter the API host for the Sunshine Conversations region being used (either api.smooch.io for the US or api.eu-1.smooch.io for the EU).

![](../../../assets/integrations/add-sunshine-integration.gif)
