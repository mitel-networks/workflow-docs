---
layout: default
title: MiCC-B
parent: Integrations
nav_order: 4
---

## MiContact Center Business (MiCC-B)

Connections to MiCC-B are managed through OAuth Authentication. Connections to MiCC-B require internet access through a public proxy OR via MBG. All connections MUST be SSL enabled.

MiCC authentication docs are located on your host servers MiCC SDK i.e. https://YOUR-HOST/miccsdk

There are two primary methods to access the WebSDK for MiCC over REST
1) User credentials - i.e. using a valid user account.
- Useful for demonstration purposes but not recommended for production integrations. NOTE: that MiCC SDK APIs may have security role requirements when using this technique
2) Service credentials - i.e. using a trusted service account on the MiCC server
- To add a client id and client secret to the MiCC server browse to the MiContactCenter\WebSites\AuthorizationServer\Configuration\clients.config file on the MiCC server. The client id is your application's name, and the client secret is a GUID that you generate. These will be your service credentials.

### Ensure the following
- You can successfully access https://YOUR-HOST/miccsdk & https://YOUR-HOST/authorizationserver from the internet
- You have access to either 1) a set of user credentials that match the role and security requirements for your integration or 2) a secure set of service credentials.

### Adding the integration in Workflow Studio
Under Library -> Integrations click "Add New" and find MiContact Center Business. 
If using 'User Credentials' choose 'http_oauth_password' click add
If using 'Service Credentials' choose 'http_oauth2_client_credentials


Once the integration is added click "Complete Setup" and enter the client_id and client_secret in the provided boxes. In the host box you will enter the host name for your instance i.e. 'my-server-.mycompany.com'

![](../../../assets/integrations/micc-b-connection.gif)