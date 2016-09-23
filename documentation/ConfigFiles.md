Back to [Home](../Readme.md)

Status: **Request For Comment** -> Candidate Recommendation -> Standard Recommendation

## Why Needed

A Variety of configuration files are needed, from those to configure the deployment tool, to those describing the target MarkLogic environment, to packaging API and rest search option configuration files. Standards are needed for each of these files.

## Current Situation

### mljsadmin

The environment configuration is assumed to be defined in ./config/env.json. This includes hostname, port, usernames, passwords, and other high level environment configuration. This is the minimum information required to talk to MarkLogic.

Currently, further configuration exists in the ./data/restapi.json file. This includes a list of REST extensions, transforms and triggers that this application consists of. Thus this is application configuration.

Further config is also saved elsewhere. This is because it is typically 'captured' from the running system using the available methods in the standard REST API or packaging API. These include:-
- ./packages/databases/contentdbconfig.xml - The Content Database configuration from the server (packaging API XML)
- ./packages/databases/modulesdbconfig.xml - The Modules Database configuration from the server (packaging API XML)
- ./data/mljs-workplace.xml - A single XML holding all MLJS Workplace page configuration (to be loaded in to content db for the application to work)

### Roxy

TODO

## Requirements

The system MUST:-

- TODO

The system SHOULD:-

- TODO

The system MAY:-

- TODO

## Recommendation

TODO
