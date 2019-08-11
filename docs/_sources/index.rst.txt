

Welcome to DJ's azure documentation!
=======================================

.. toctree::
   :maxdepth: 4
   :caption: Contents:


Table of contents
-----------------

-  `Azure DevOps`_

-  `What is Azure Pipeline?`_

-  `Create an Azure Pipeline for a GitHub repo`_

-  `Customize your pipeline in two ways`_

-  `Pipeline structures`_

-  `Reference`_

Azure DevOps
------------

-  Overview
-  Boards

   -  Work Items (``Issue``, ``Epic``, ``Task``)
   -  Sprints(\ ``Schedule``) etc

-  Repo: git repo (e.g. clone, fork etc)
-  Pipeline
-  Test Plan: more for large organization
-  Artifacts: more for a small team

   -  Create new feed and use in the pipelines

What is Azure Pipeline?
-----------------------

Azure Pipelines is a cloud service that you can use to automatically
**build and test** your code project and make it available to other
users. It works with just about any language or project type.

Azure Pipelines combines **continuous integration (CI)** and
**continuous delivery (CD)** to constantly and consistently test and
build your code and ship it to any target.

+------------------+-------------------------+-------------------------+
|                  | Continuous integration  | Continuous delivery     |
|                  | (CI)                    | (CD)                    |
+==================+=========================+=========================+
| 1                | Automatically ensure    | Automatically deploy    |
|                  | you don’t ship broken   | code to production.     |
|                  | code.                   |                         |
+------------------+-------------------------+-------------------------+
| 2                | Build faster by         | Ensure deployment       |
|                  | splitting test and      | targets have latest     |
|                  | build run               | code.                   |
+------------------+-------------------------+-------------------------+
| 3                | Run tests continually.  | Use tested code from CI |
|                  |                         | process.                |
+------------------+-------------------------+-------------------------+
| 4                | Increase code coverage. |                         |
+------------------+-------------------------+-------------------------+

Create an Azure Pipeline for a GitHub repo
-----------------------------------------------------

-  On GitHub

   -  Register a GitHub account
   -  Create a new ``public`` repo (e.g. ``azure``) and push an initial
      commit (e.g. ``README.md``)

-  On Azure

   -  Sign up an an Azure DevOps account
   -  Add an Azure DevOps organization
   -  Add a ``public`` Azure project
   -  In the project, navigate to the ``Pipiline`` page
   -  Select the GitHub repo ``azure``
   -  Build a new pipeline following the `tutorial`_ 

Customize your pipeline in two ways
-----------------------------------

   -  Edit a yml file on Azure DevOps project/pipeline/Builds => Commit and
      Run => The yml file will be pushed to GitHub automatically

   -  Push a new yml file to GitHub => On Azure DevOps, select
      ``Existing Azure pipeline YAML file`` => Select the yml on GitHub

Pipeline structures
-------------------

   -  Stage

      -  Major divisions in a pipeline
      -  By default, stages run sequentially
      -  e.g. \ ``build this app``, ``run these tests``, and
         ``deploy to pre-production``

   -  Job

      -  Jobs can be run conditionally, and they may depend on earlier
         jobs.

      -  A collection of steps to be run by an agent or on the server.

   -  Step

      -  A linear sequence of operations that make up a job

      -  Each step runs in its own process on an agent and has access to
         the pipeline workspace on disk.

      -  This means environment variables are not preserved between steps
         but filesystem changes are.

   -  Variables

      -  Hardcoded values can be added directly, or variable groups can be
         referenced.

      -  Variables may be specified at the pipeline, stage, or job level.

Reference
---------

      -  `Intro to Azure DevOps - Source Control, CI/CD, Automation`_

      -  `Azure Pipelines Doc`_

         -  `Jobs`_
         -  `Variables`_
         -  `Pipelines-anaconda`_
         -  `Run pipelines with Anaconda`_
         -  `Continuous Builds for master branch and pull request`_
         -  `Deploy a Python web app using CI/CD to Azure App Service`_

      -  `YAML schema reference`_

         -  `Learn YAML in Y minutes`_

      .. _tutorial:  https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2
      .. _Intro to Azure DevOps - Source Control, CI/CD, Automation: https://www.youtube.com/watch?v=H-R2bCXfz8I
      .. _Azure Pipelines Doc: https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops
      .. _Jobs: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/phases?view=azure-devops&tabs=yaml
      .. _Variables: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch
      .. _Pipelines-anaconda: https://github.com/MicrosoftDocs/pipelines-anaconda
      .. _Run pipelines with Anaconda: https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/anaconda?view=azure-devops&tabs=macos
      .. _Continuous Builds for master branch and pull request: https://www.youtube.com/watch?v=vlBuNM6Wzic
      .. _Deploy a Python web app using CI/CD to Azure App Service: https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/python-webapp?view=azure-devops
      .. _YAML schema reference: https://docs.microsoft.com/en-us/azure/devops/pipelines/yaml-schema?view=azure-devops&tabs=schema
      .. _Learn YAML in Y minutes: https://learnxinyminutes.com/docs/yaml/
