Back to [Home](../README.md)

Status: **Request For Comment** -> Candidate Recommendation -> Standard Recommendation

## Why needed

A standard foldering layout will allow inclusion of all MarkLogic application configuration within any build tool framework, and provide consistency. A single app layout will be deployable within a variety of tools.

## Current situations

Current tools use the following:-

Area | Roxy | RXQ | mljsadmin | ml-gradle
---- | ---- | ---- | ---- | ----
Root folder | ? | ? | mljsadmin.log file only | project root
Tool configuration | deploy | ? | config (some in ./data/restapi.json) | build.gradle
Web app folder | src/app (mixed) | ? | app | N/A
ML modules folder | src/app (mixed) | ? | modules | src/main/ml-modules
ML rest extensions | rest-api/ext | ? | rest-api/ext | src/main/ml-modules/ext
ML rest resources | rest-api/resources | ? | rest-api/resources | src/main/ml-modules/services
ML search options | rest-api/config/options | ? | restapi/config/options | src/main/ml-modules/options
ML server configuration | deploy | ? | packages | src/main/ml-config
Unit tests | test and src/test | ? | N/A | src/test/java
Data folder | data | ? | data | data
Documentation | ? | ? | docs | N/A
Internal or transient | deploy | ? | node_modules | .gradle

## Requirements

The system MUST:-

- Use a single, uniquely named, parent folder so as to minimise the interference with build tool specific folder layouts
- Store all MarkLogic configuration, runtime, database exports, data, and everything else for the MarkLogic application within that structure
- Store different classes of configuration under sub folders
- Support at least a single environment (MarkLogic server settings), packaging API configuration, content to load

The system SHOULD:-

- TODO

The system MAY:-

- TODO

## Recommendation
