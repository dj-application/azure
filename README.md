# Azure

[![Build Status](https://dev.azure.com/dj-azure/dao1/_apis/build/status/dj-application.azure?branchName=master)](https://dev.azure.com/dj-azure/dao1/_build/latest?definitionId=1&branchName=master)

---

## Table of contents
- [Azure pipeline](#azure)
- [Azure pipeline for a GitHub repo](#github)


## What is Azure pipeline?

[Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops) is a cloud service that you can use to automatically **build and test** your code project and make it available to other users. It works with just about any language or project type.

Azure Pipelines combines **continuous integration (CI)** and **continuous delivery (CD)** to constantly and consistently test and build your code and ship it to any target.

|   |Continuous integration (CI)   |Continuous delivery (CD)   |
|---|:---|:---|
|1|Automatically ensure you don't ship broken code.   |Automatically deploy code to production.   |
|2|Build faster by splitting test and build run   |Ensure deployment targets have latest code.   |
|3|Run tests continually.   |Use tested code from CI process.     |
|4|Increase code coverage.   | |


### Create an Azure pipeline to build a GitHub repository

- On GitHub
   * Register a GitHub account
   * Create a new `public` repo (e.g. `azure`) and push an initial commit (e.g. `README.md`)
- On Azure
   * Register [an Azure organization account](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/pipelines-sign-up?view=azure-devops)
   * Add an Azure DevOps organization
   * Add a `public` Azure project
   * In the project, navigate to the `Pipiline` page
   * Select the GitHub repo `azure`
   * Build a new pipeline following the [tutorial](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2)
