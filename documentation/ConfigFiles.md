Back to [Home](../README.md)

Status: **Request For Comment** -> Candidate Recommendation -> Standard Recommendation

## Why?

Configuration files are needed to ensure that tools are able to quickly integrate into any MarkLogic environment without making complicated source code changes to do so. Configuration files may define which version of MarkLogic is being used, hostnames and port numbers, user credentials and even what operations the tool should perform. Configuration files should adhere to a common set of standards, thus making it easy for developers to quickly switch between tools. Additionally, configuration files have the added benefit of being versionable and easily disseminated to developers via a version control mechanism such as git or subversion.

## Current Situation

### mljsadmin

The environment configuration is assumed to be defined in ./config/env.json. This includes hostname, port, usernames, passwords, and other high level environment configuration. This is the minimum information required to talk to MarkLogic.

Currently, further configuration exists in the ./data/restapi.json file. This includes a list of REST extensions, transforms and triggers that this application consists of. Thus this is application configuration.

Further config is also saved elsewhere. This is because it is typically 'captured' from the running system using the available methods in the standard REST API or packaging API. These include:-
- ./packages/databases/contentdbconfig.xml - The Content Database configuration from the server (packaging API XML)
- ./packages/databases/modulesdbconfig.xml - The Modules Database configuration from the server (packaging API XML)
- ./data/mljs-workplace.xml - A single XML holding all MLJS Workplace page configuration (to be loaded in to content db for the application to work)

### Roxy

Roxy relies on two types of configuration files : Properties files and "ml-config" XML files.

Properties files are text files which define variables such as connection information (hostname, port numbers, etc.), user credentials, settings unique to Roxy and values for infrastructure deployment (which ml-config file to use, etc.).

There are three levels of properties files which Roxy looks at when performing a deployment : default.properties are default values that Roxy ships with. These values may change when Roxy is upgraded. build.properties are default properties for your application that override the values in default.properties. build.properties will not change when Roxy is upgraded. Finally, environment properties (local.properties, dev.properties, prod.properties, etc.) are properties which are environment specific and override any selections made in build.properties. Any properties file may store the same value as any other properties file. However, its best to keep properties files as minimal as possible for clarity.

ml-config files are XML files which define the MarkLogic infrastructure that Roxy may deploy or wipe. This infrastructure includes things such as forests, databases, indexes, roles, REST instances and more. Unlike properties files, only one ml-config file may be leveraged for each environment. ml-config files may use values taken from the variables defined in Roxy's properties files.

## Requirements

The tool MUST:-

* Use configuration files to allow users to easily switch between different MarkLogic environments
* Allow hostname, ports and user credentials to be defined

The tool SHOULD:-

* Allow some configuration options to be overriden on the commandline at runtime
* Abstract as much logic of its operations into configuration files as possible to avoid needing to touch the tool's code

The tool MAY:-

* Simultaneously support multiple MarkLogic environments at once
* Allow configuration files to be used from a remote location (git, another server, etc.)

## Recommendation

TODO
