---
layout: default
title: Salesforce
parent: Integrations
nav_order: 3
---

## Salesforce

Note the information below comes primarily from the third party vendor. Website links / wording and steps may change without notice. 

Connections to salesforce are managed through salesforce connected apps. The typical steps are to 1 - create a connected app 2 - configure the connected app for OAuth settings for API integration

[Salesforce connected apps](https://help.salesforce.com/articleView?id=connected_app_create.htm){:target="_blank"}

Follow the steps under "Configure Basic Connected App Settings" and then "Enable OAuth Settings for API Integration".

To allow workflow to authenticate with salesforce you must give it the salesforce connection URL of the Mitel workflow service. https://workflow.us.api.mitel.io/2017-09-01/integrations/salesforce/sso as well as give permissions to the appropriate scopes.

See below for a sample visual of the typical OAuth settings for a connected app.

![](../../../assets/integrations/salesforce-connected-app.png)

## Actions Available

### Salesforce Object Query Language (SOQL) Query
Query any salesforce object in the system using the Salesforce Object Query Language (SOQL). SOQL is a powerful language giving you to query information across your entire salesforce instance.

[Salesforce Object Query Language (SOQL)](https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/sforce_api_calls_soql.htm){:target="_blank"}

### Salesforce Get Record Field Values
Get a sub-set of values from a salesforce record. Typically salesforce records can be large and this allows for explicit targetted field access for any valid salesforce record

[Get Field Values from a Standard Object Record](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/dome_get_field_values.htm){:target="_blank"}

### Salesforce Create or Update Record
Create or update any record in Salesforce in JSON format

[Create a Record](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/dome_sobject_create.htm){:target="_blank"}

[Update a Record](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/dome_update_fields.htm){:target="_blank"}