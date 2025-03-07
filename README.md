# 20 CI-CD: GitHub Actions CI/CD Setup

## User Story

```md
AS A developer looking to integrate a pipeline in a codebase for continuous integration and deployment, 
I WANT to create a GitHub Action that will follow best practices by running test cases when a Pull Request is made to the develop branch
SO THAT I can ensure that all code integrations are clean and pass the proper requirements.

AS A developer looking to deploy the application automatically to Render when code is merged from develop to main,
I WANT to create a GitHub Action that will run when the code is merged to main and automatically deploys to Render
SO THAT the application is constantly updated when major releases are made to the main branch.
```

## Infrastructure setup

> * In this code, Setup "Deploy" YAML to use a variable from Render DEPLOY_URL: ${{ secrets.RENDER_DEPLOY_HOOK_URL }}
>
> * In Render https://dashboard.render.com/, create a 'Static Site'
>
> * In the project Settings, copy the 'Deploy Hook'
>
> * Publish Directory set as './server/dist'
>
> * In this project's GitHub repo, go to settings. Go to Secrets and variables - Action
>
> * Create a Repository secret and name it 'RENDER_DEPLOY_HOOK_URL' and paste the value from Render 'Deploy Hook'

# GitHub Repo 
https://github.com/MrAwesome2127/KU-20-CICD

* In this code, Setup "Deploy" YAML to use a variable from Render DEPLOY_URL: ${{ secrets.RENDER_DEPLOY_HOOK_URL }}

* In this project's GitHub repo, go to settings. Go to Secrets and variables - Action

* Create a Repository secret and name it 'RENDER_DEPLOY_HOOK_URL' and paste the value from Render 'Deploy Hook'
  
* Branches - main, develop, feature

* yaml

  * deploy - will deploy to render

  * test - will be for test with Cypress to be executed

# Render 
*Changing*

* In Render 'https://dashboard.render.com/', create a 'Web Service'

  * In the project Settings, copy the 'Deploy Hook'

  * Setup the env variable for MongoDB

# MongoDB

* Obtain your password.
  
* Whitelist your DB access https://www.mongodb.com/docs/atlas/security/ip-access-list/
  
* 1 In Atlas, go to the Project Settings page.
  * If it's not already displayed, select the organization that contains your desired project from the  Organizations menu in the navigation bar.

  * If it's not already displayed, select your desired project from the Projects menu in the navigation bar.

  * Next to the Projects menu, expand the  Options menu, then click Project Settings.


* 2 In Atlas, go to the Project Activity Feed page.
If it's not already displayed, select the organization that contains your desired project from the  Organizations menu in the navigation bar.

  * If it's not already displayed, select your desired project from the Projects menu in the navigation bar.

  * Do one of the following steps:

    * Click the Project Activity Feed icon in the right side of the navigation bar.

    * Next to the Projects menu, expand the  Options menu, click Project Settings, and click Activity Feed in the sidebar.

## Add IP Access List Entries

* 1 In Atlas, go to the Network Access page for your project.
  * If it's not already displayed, select the organization that contains your project from the  Organizations menu in the navigation bar.

  * If it's not already displayed, select your project from the Projects menu in the navigation bar.

  * In the sidebar, click Network Access under the Security heading.
* 2 Go to IP Access List view.
  * If it isn't already displayed, click the IP Access List tab.

  * Click  Add IP Address.

* 3 Enter an IP address, CIDR block, or Security Group ID.
