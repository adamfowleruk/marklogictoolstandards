# MarkLogicToolStandards

Welcome to the MarkLogic Tool Standards project!

This project aims to provide useful standards, best practices, and guidance around laying out applications that target MarkLogic. This will allow all the open source deploy tools (Roxy, mjlsadmin, ml-gradle et al) to use the same source application folder layouts - providing consistency amongst all application deployments.

This in turn will allow developers to choose their favourite tools safe in the knowledge that the same distributed application will work with their preferred toolset.

By providing overviews this project also attempts to prevent overlap and competition between tools, usually caused by unawareness. It can also be used as reference to find the toolset that suits your needs best.

## Vision

Ideally we have toolsets with full coverage for all mainstream languages, that operate in a consistent way, and can be interchanged at any time.

## Principles

Below a list of thumb rules to provide some overall guidance and ground rules:

- (Ideally) full coverage for each mainstream language
- No overlap between tools within a language
- Optimal use of facilities provided OOTB with MarkLogic (e.g. Management REST API)
- Consistency in configuration (primarily terminology)
- Consistency in folder structures
- Isolation of deployment tool for easy exchange

## Definitions

### Mainstream languages

Mainstream languages is not a well-defined term. If you search on internet, you mostly find lists of most popular languages. For this project it makes more sense to look at most used languages though, so based on volume rather than number of Google/Yahoo searches. The results on the [TIOBE Index](http://www.tiobe.com/tiobe-index/) look reasonable though (Sept 2016 list):

1.  Java (18.236%)
2.  C (10.955%)
3.  C++ (6.657%)
4.  C# (5.493%)
5.  Python (4.302%)
6.  JavaScript (2.929%)
7.  PHP (2.847%)
8.  Assembly (2.417%)
9.  .NET (2.343%)
10. Perl (2.333%)

For constrast, coverage of languages on Github looks quite different, based on [Githut.info](http://githut.info/) (2014 Q4, number of repositories):

1.  JavaScript (324k)
2.  Java (223k)
3.  Python (165k)
4.  CSS (164k)
5.  PHP (139k)
6.  Ruby (133k)
7.  C++ (87k)
8.  C (73k)
9.  Shell (66k)
10. C# (56k)

Looking at above lists, we can safely say, primary focus should be on:

-  Java
-  Python
-  JavaScript
-  C
-  C++
-  PHP
-  C#

And since we already cover that in the past:

- .Net

## Progress
### Phase 1 - Document what is there

We're documenting the tools available right now, and what we want them to do.

- [What tools are available?](documentation/ToolList.md)
- [Current Tool Deployment Tasks](documentation/DeployTasks.md)

### Phase 2 - Agree goals

We need to agree the goals of the project/effort.

- [Goals of the project](documentation/Goals.md)

### Phase 3 - Create standards road map

All of the below are a work in progress...

- [Application Foldering Layout](documentation/Foldering.md)
- [Target Environment Configuration Files](documentation/ConfigFiles.md)

### Phase 4 - Implement standards in tools

TODO define which tools will implement what, by when.
