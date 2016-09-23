Back to [Home](../README.md)

Status: **Request For Comment** -> Candidate Recommendation -> Standard Recommendation

## Why Needed

A developer should be able to pick up their favourite deploy tool and run the same command there as a deploy tool in a different environment.

## Current situation in some tools

Task | Roxy/mlsound | mljsadmin | ml-gradle
---- | ---- | ---- | ----
Create application scaffolding | init/create | N/A | mlScaffold
Initialise tool | init | N/A | N/A
Create config files | init | N/A | N/A
Print config information | info | N/A | --info
Specify environment configuration to use | CMD ENVNAME | --conf=CONFFILE | Gradle properties plugin
Create environment | bootstrap | install | mlDeploy
Create REST API instance (content db) | ? | --install=restapi | mlCreateResource
Create REST API instance (modules db) | ? | --install=modulesrestapi | mlCreateResource
Deploy ML modules | deploy modules | --install=modules | mlLoadModules or mlReloadModules
Deploy web app | deploy modules | N/A (runs in node) | N/A
Deploy rest extensions | ? | --install=extensions | mlLoadModules
Deploy rest resources | ? | N/A | mlLoadModules
Deploy triggers | ? | --install=triggers $ | mlDeployTriggers
Deploy alert config | ? | ? | mlDeployAlertConfig
Update search options | ? | --update=searchoptions | mlLoadModules
Update database configuration (content) | ? | --update=dbconfig | mlDeployDatabases
Update database configuration (modules) | ? | --update=modulesdbconfig | mlDeployDatabases
Update installed ontology | ? | --update=ontology | N/A
Update MLJS Workplace config | ? | --update=workplace $ | N/A
Copy in content | deploy data | load or --load=/some/folder | Use MlcpTask or roll your own Gradle task
Remove content from server | clean | clean | mlClearContentDatabase
Get config from server | N/A | capture | N/A
Get database config (content) | ? | --capture=dbconfig | N/A
Get database config (modules) | ? | --capture=modulesdbconfig | N/A
Get deployed ontology | N/A | --capture=ontology | N/A
Get deployed web app config | N/A | --capture=workplace $ | N/A
Get deployed search options | N/A | --capture=searchoptions | N/A
Get deployed triggers config | ? | --capture=triggers $ | N/A
Restart MarkLogic | restart | N/A | mlRestartCluster
Run tests | test | N/A | test
Initialise application to pre-demo state | ? | reset | Custom Gradle task
Removing environment | wipe | remove | mlUndeploy
Remove REST API (content DB) | ? | --remove=dbconfig | mlUndeploy
Remove REST API (modules DB) | ? | --remove=modulesdbconfig | mlUndeploy
Remove REST extensions | ? | --remove=extensions | mlClearModules
Remove Triggers | ? | --remove=triggers $ | mlClearTriggers

Note that $ means the function requires a server side extension. E.g. REST extension or some other functionality

A note about ml-gradle tasks - because ml-gradle is a plugin, and there could be dozens, if not hundreds, of other Gradle tasks in a project, "ml" is used as a prefix for all ml-gradle tasks. Gradle also does not require typing the full task name nor is it case-sensitive - i.e. typing "gradle mlreload" will invoke "mlReloadModules" as long as no other task starts with "mlreload".

## Known Requirements

Things the tools currently do:-

- Share pieces of code, and allow them to be fetched and integrated to a project
- Set up a cluster
- Configure a server
- Deploy a project to a server
- Run a web app/project
- deploy content in to MarkLogic, remove it, etc.
- Live admin tools for changing something on a server (restart, detach forest, etc.)
- Link in to REST Management/Packaging API via some connector language
