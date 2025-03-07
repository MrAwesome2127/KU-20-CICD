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

### GitHub Repo https://github.com/MrAwesome2127/KU-20-CICD

* In this code, Setup "Deploy" YAML to use a variable from Render DEPLOY_URL: ${{ secrets.RENDER_DEPLOY_HOOK_URL }}

* In this project's GitHub repo, go to settings. Go to Secrets and variables - Action

* Create a Repository secret and name it 'RENDER_DEPLOY_HOOK_URL' and paste the value from Render 'Deploy Hook'
  
* Branches - main, develop, feature

* yaml

  * deploy - will deploy to render

  * test - will be for test with Cypress to be executed

### Render *Changing*

* In Render 'https://dashboard.render.com/', create a 'Static Site'

  * Publish Directory set as './server/dist'

  * In the project Settings, copy the 'Deploy Hook'