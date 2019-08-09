[![Board Status](https://dev.azure.com/dj-azure/36a60840-a111-4d3e-9c86-8f2e7ca54333/8daccbf9-d4b9-4419-9bc8-5c14e6d7ed47/_apis/work/boardbadge/6115b2ba-9d24-4833-b573-e04d19352cd7)](https://dev.azure.com/dj-azure/36a60840-a111-4d3e-9c86-8f2e7ca54333/_boards/board/t/8daccbf9-d4b9-4419-9bc8-5c14e6d7ed47/Microsoft.RequirementCategory)
# Azure

[![Build Status](https://dev.azure.com/dj-azure/dao1/_apis/build/status/dj-application.azure?branchName=master)](https://dev.azure.com/dj-azure/dao1/_build/latest?definitionId=1&branchName=master)   [![Build Status](https://dev.azure.com/dj-azure/dao1/_apis/build/status/dj-application.azure%20(3)?branchName=master)](https://dev.azure.com/dj-azure/dao1/_build/latest?definitionId=5&branchName=master)
---

## Table of contents

- [Azure Pipeline](#azure)

- [Azure Pipeline for a GitHub repo](#github)

- [Customize your pipeline](#customize)

- [Pipeline structures](#structure)

- [Reference](#ref)

## What is Azure Pipeline?

[Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops) is a cloud service that you can use to automatically **build and test** your code project and make it available to other users. It works with just about any language or project type.

Azure Pipelines combines **continuous integration (CI)** and **continuous delivery (CD)** to constantly and consistently test and build your code and ship it to any target.

|   |Continuous integration (CI)   |Continuous delivery (CD)   |
|---|:---|:---|
|1|Automatically ensure you don't ship broken code.   |Automatically deploy code to production.   |
|2|Build faster by splitting test and build run   |Ensure deployment targets have latest code.   |
|3|Run tests continually.   |Use tested code from CI process.     |
|4|Increase code coverage.   | |


## Create an Azure Pipeline to build a GitHub repository

- On GitHub
   * Register a GitHub account
   * Create a new `public` repo (e.g. `azure`) and push an initial commit (e.g. `README.md`)
- On Azure
   * Sign up an [an Azure DevOps account](https://azure.microsoft.com/en-us/services/devops/pipelines/)
   * Add an Azure DevOps organization
   * Add a `public` Azure project
   * In the project, navigate to the `Pipiline` page
   * Select the GitHub repo `azure`
   * Build a new pipeline following the [tutorial](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2)


## Customize your pipeline
  * Edit a yml file on Azure DevOps project/pipeline/Builds => Commit and Run => yml file will be pushed to GitHub automatically  

  * Push a new yml file to GitHub => On Azure DevOps, select `Existing Azure pipeline YAML file` => Select the yml on GitHub


## Pipeline structures

- Stage
  * Major divisions in a pipeline   
  * By default, stages run sequentially
  * e.g. `build this app`, `run these tests`, and `deploy to pre-production`

- Job
   * Jobs can be run conditionally, and they may depend on earlier jobs.

   * A collection of steps to be run by an agent or on the server.


-  Step  
   * A linear sequence of operations that make up a job

   * Each step runs in its own process on an agent and has access to the pipeline workspace on disk.

   * This means environment variables are not preserved between steps but filesystem changes are.


-  Variables
   * Hardcoded values can be added directly, or variable groups can be referenced.   

   * Variables may be specified at the pipeline, stage, or job level.


---
## Reference
 * [Run pipelines with Anaconda environments](https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/anaconda?view=azure-devops&tabs=macos)
 * [pipelines-anaconda](https://github.com/MicrosoftDocs/pipelines-anaconda)
 * [Deploy a Python web app using CI/CD to Azure App Service on Linux](https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/python-webapp?view=azure-devops)
 * [Learn in Y minutes](https://learnxinyminutes.com/docs/yaml/)
 * [YAML schema reference](https://docs.microsoft.com/en-us/azure/devops/pipelines/yaml-schema?view=azure-devops&tabs=schema)
 * [Jobs](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/phases?view=azure-devops&tabs=yaml)
 * [Variables](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch)
