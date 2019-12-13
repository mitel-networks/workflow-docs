---
layout: default
title: Import / Export
parent: Advanced
nav_order: 1
---
# General

Recipes, Flows, Actions and Triggers are all ultimately stored in a standard JSON format text file (\*.json).

At runtime these objects will be restored for execution from their JSON source files.

# Import

Importing supports either a persisted \*.json file OR a block of plain text that conforms to the JSON format.

Whether importing by file or text the following conditions must also be met for a successful import:

* The contained JSON must describe a valid Recipe, Flow, Action or Trigger.

* The type of object described by the JSON must match the intended import type - meaning for example importing a Trigger as an Action is not allowed.

After a successful import:

* The imported object will be assigned a new internal ID and is considered a unique entity, distinct from the original source of the JSON

## Common Usage

* Restoring Recipes, Flows, Actions and Triggers from backup JSON files.

* An alternative method of cloning Recipes, Flows, Actions and Triggers.

# Export

Exporting creates a JSON format copy of a Recipe, Flow, Action or Trigger.

Unless otherwise specified:

* Exported JSON will include any pending changes to an object

## Common Usage

* Creating backup copies of Recipes, Flows, Actions and Triggers.

* Creating useful documents to have on hand when contacting support. 
