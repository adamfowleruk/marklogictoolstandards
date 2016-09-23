Back to [Home](../README.md)

## Goals of the project

This project aims to document what tools are available for MarkLogic, create consensus on the features required,
create standards around how to support the features, and implement the features in a suite/suites of tools.

## Purpose of the tools

Below are the things those using MarkLogic Server need to accomplish.

### Configuring (including creation) of a MarkLogic Server instance or cluster

- Take a 'blank' fresh ML Server install, and bootstrap it (join to cluster, admin info, etc) - E.g. from an AWS AMI launch
- Creating database, forests, modules db, REST API server, and configuring them

### Deployment of a MarkLogic Server application

- Configuring the content db for indexes
- Adding application roles, privileges, users
- Deploying modules DB
- Deploying CPF modules
- Deploying REST extensions
- Deploying transforms
- Capturing current application and/or server configuration for deployment elsewhere
- Creating an application folder/package for sharing 

### Sharing code snippets or assets, below the application level

- Packaging a set of XQY/SJS files for inclusion in other projects
- Maintaining a central list of packages for download
- Searching for and installing a package inside an application folder
- Describing and publishing a new package  

### Administration of a running MarkLogic server or cluster

- Restart a server
- Disable/enable a CPF Domain
- Perform a backup

### Interaction with a MarkLogic Server application

For example:-

- Loading, modifying, deleting content in a MarkLogic database
- Calling REST API functions


### Testing an application

- Calling REST API functions in a scripted repeatably manner
- Providing pass/fail feedback on those interactions
- XQuery/SJS web app testing?
