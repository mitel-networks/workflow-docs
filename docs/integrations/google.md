---
layout: default
title: Google
parent: Integrations
nav_order: 5
---

## Google

Note the information below comes primarily from the third party vendor. Website links / wording and steps may change without notice. 

## Using OAuth 2.0 for Server to Server Applications

Connections to Google are managed through OAuth and a GCP service account. Workflow will call Google APIs on behalf of the service account.
For more information about authentication of GCP service accounts see below.

https://developers.google.com/identity/protocols/oauth2/service-account
https://cloud.google.com/iam/docs/creating-managing-service-account-keys

Follow the instructions for Creating a service account including creating a key and download the json file to your machine.

From the json file you need the client_email and private_key and you will also need to know the scopes you need to request.

https://developers.google.com/identity/protocols/oauth2/scopes

To add the integration go to the Integrations section, select Google and click add of the http_oauth2_jwt_bearer integration.

Once added click Complete Setup and enter the information from the service account key and the required scopes (a space-delimited list if multiple) and click Create.

