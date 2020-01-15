---
layout: default
title: Call Display Extensions (Alpha 0.0.1)
parent: Walkthroughs
nav_order: 4
---

## Supported applications
Call display extensions are currently in draft alpha proposal and only implemented in MOMA web (beta) at the present time. Future plans are to extend this out to MOMA mobility and MiCollab after the standard moves past alpha status. Conversion to Mitel XML for 6800 & 6900 displays is also under consideration but not in place at this time.

## What is it?
Call display extensions allow you to 
1 - trigger actions based on call state change events
2 - display custom call meta data on the call screens
3 - display custom mid call feature buttons that can be tied to call control commands and / or commands for external systems.

## Common use cases
Some common use cases would be 
1 - Screen pops - very common in the contact center space but now could be made available to general UC deployments under certain circumstances
2 - Custom mid call feature buttons when connected to legacy systems. Consider that our legacy PBX systems support significant amounts of mid call features via DTMF codes. These features can now be easily displayed as mid call feature buttons based on conditions.
3 - Silently trigger actions like third party call loggers by using the silent actions command pre or post call.

## How to use
To invoke a call display extension you simply tag an active call via any means. Using the workflow tag call activity via a call handling script is the most likely scenario.
The call tag can simply be a basic key (string) and value (string) which would trigger a basic string display on the call screen. Or it can be a complex behaviour using our call display extensibility language.
NOTE: We need to decide if we support both. Supporting the basic key | value tags may cause issues as tags couldn't be used for other purposes.

## Call Display Presentation Language

Simple example showing a textual label onto the call screen

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "cust-status",
        "type": "Text",
        "text": "Gold",
        "formFactor", "All"
    }]
}
```

Custom mid call feature button displaying a park key

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "park",
        "type": "Button",
        "text": "Park",
        "formFactor", "All",
        "primaryAction": {
            "type": "DTMF",
            "target": "",
            "payload": "1234#"
        }
    }]
}
```

Screen pop

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "screenpop",
        "type": "Action",
        "text": "none",
        "formFactor", "All",
        "primaryAction": {
            "type": "Action",
            "target": "https://google.com"
        }
    }]
}
```

Screen pop with conditions.. example using when clause

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "screenpop",
        "type": "Action",
        "text": "none",
        "formFactor", "All",
        "when": '"${state}" == "RINGING"',
        "primaryAction": {
            "type": "Action",
            "target": "https://google.com"
        }
    }]
}
```

Button setting context

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "my-set-var-item",
        "type": "Button",
        "text": "Set foo",
        "formFactor", "All",
        "primaryAction": {
            "type": "SetContextValue",
            "target": "foo",
            "payload": "bar"
        }
    }]
}
```

Button conditional on SetContextValue

``` javascript
{
    "contentType": "application/vnd.mitel.call-display-extensions",
    "version": "0.0.1",
    "items": [ {
        "itemId": "my-set-var-item",
        "type": "Button",
        "text": "Bar",
        "formFactor", "All",
        "when": "${foo}" == "bar",
        "primaryAction": {
            "type": "OpenUrl",
            "target": "https://google.com"
        }
    }]
}
```