Back to [Home](../README.md)

Status: **Request For Comment** -> Candidate Recommendation -> Standard Recommendation

## Why Needed

A developer should be able to pick up their favourite deploy tool and run the same command there as a deploy tool in a different environment.

## Current situation in some tools

Task | Roxy | mlsound | mljsadmin | ml-gradle
---- | ---- | ---- | ---- | ----
Create application scaffolding | init/create | new project-name | N/A | mlScaffold
Initialise tool | init | N/A |N/A | N/A
Upgrade tool | upgrade | N/A | ? | ?
Create config files | init | N/A | N/A | N/A
Print config information | info | N/A | N/A | --info
Specify environment configuration to use | CMD ENVNAME | -e ENVNAME | --conf=CONFFILE | Gradle properties plugin
Create environment | bootstrap | bootstrap | install | mlDeploy
Create REST API instance (content db) | ? | bootstrap |  --install=restapi | mlCreateResource
Create REST API instance (modules db) | ? | bootstrap | --install=modulesrestapi | mlCreateResource
Deploy ML modules | deploy src or deploy modules | deploy code | --install=modules | mlLoadModules or mlReloadModules
Deploy web app | deploy modules | deploy code | N/A (runs in node) | N/A
Deploy rest extensions | deploy ext or deploy modules |deploy code | --install=extensions | mlLoadModules
Deploy rest resources | ? |deploy code | N/A | mlLoadModules
Deploy triggers | deploy triggers |deploy triggers | --install=triggers $ | mlDeployTriggers
Deploy alert config | In progress.. |deploy alerts | ? | mlDeployAlertConfig
Update search options | ? | deploy code | --update=searchoptions | mlLoadModules
Update database configuration (content) | ? | bootstrap |  --update=dbconfig | mlDeployDatabases
Update database configuration (modules) | ? | bootstrap | --update=modulesdbconfig | mlDeployDatabases
Update installed ontology | ? | N/A | --update=ontology | N/A
Update MLJS Workplace config | ? | N/A | --update=workplace $ | N/A
Copy in content | deploy data also supports MLCP | deploy data | load or --load=/some/folder | Use MlcpTask or roll your own Gradle task
Remove content from server | clean | clean | clean | mlClearContentDatabase
Get config from server | N/A | N/A | capture | N/A
Get database config (content) | ? | N/A | --capture=dbconfig | N/A
Get database config (modules) | ? | N/A |--capture=modulesdbconfig | N/A
Get deployed ontology | N/A | N/A |--capture=ontology | N/A
Get deployed web app config | N/A | N/A | --capture=workplace $ | N/A
Get deployed search options | N/A | N/A | --capture=searchoptions | N/A
Get deployed triggers config | ? | N/A | --capture=triggers $ | N/A
Restart MarkLogic | restart | restart | N/A | mlRestartCluster
Run tests | test | N/A | N/A | test
Initialise application to pre-demo state | ? | custom | reset | Custom Gradle task
Removing environment | wipe | wipe | remove | mlUndeploy
Remove REST API (content DB) | ? | N/A | --remove=dbconfig | mlUndeploy
Remove REST API (modules DB) | ? | N/A | --remove=modulesdbconfig | mlUndeploy
Remove REST extensions | clean ext | N/A |--remove=extensions | mlClearModules
Remove Triggers | clean triggers | clean triggers | --remove=triggers $ | mlClearTriggers
MLCP Support | yes | NO | ? | ?
CORB Support | yes | NO |? | ?



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
