![project Logo](/CypressProjectLogo.png)

# Cypress E2E testing with Azure CI/CD pipeline 
This is a project which you can use to start your E2E testing with Cypress by azure CI/CD.

- Parallel execution
- Cross Browser Testing (Using Chrome,FireFox & Edge)

Demo azure pipeline

### Cypress version : 4.5.0

# Installation  
1. Create a project directory and Clone the project: 
```git clone https://github.com/QACodeDev/cypress-pipeline-demo.git``` 
2. Under the project directory install the followings: 
```npm install```

# How to start

In order to start using this project. You will have to do the following steps:

Provide the `username`, `password`, and `baseUrl` in cypress.json and put other required test data.
 
 ## Azure DevOps setup
Start by creating a new variable group on Azure DevOps. I use two, one for my DEV branch and one for my master branch. If you only want to use one branch or one environment, you can remove the dynamic grouping expression in the azure-pipelines.yml file.
Add the following variables to the group:
CI: true
cypress_project_id: <cypress-project-id> - the ID of the project Cypress gave you.
cypress_record_key: <cypress-record-key> - If you want to record to Cypress.io.
verbose: true or false - Allows you to run the pipeline in verbose mode, and will add some extra logging. Cypress will also run in DEBUG mode by setting it to true.
In the azure-pipelines.yml file, update the dynamic group name variables from vargroup-master and vargroup-dev to your corresponding group names. 

![variable group](/variable_group.png)

## **Mulitple ways to execute the tests**:

### Using Cyperss GUI:
* Under the project directory run the following npm command: `npm run cy:open`
### Using CLI - Headless mode:
* Under the project directory run the following npm command: `npm run cy:run:headless`
### Using CLI - Chrome browser:
* Under the project directory run the following npm command: `npm run cy:chrome`
### Using CLI - firefox browser:
* Under the project directory run the following npm command: `npm run cy:firefox`
### Using CLI - edge:
* Under the project directory run the following npm command: `npm run cy:edge`
### Using CLI - For recording cypress dashboard:
* Under the project directory run the following npm command: `npm run cy:run:record`

### Using CLI - without modifying cypress.json:

* Alternative command : 
`$(npm bin)/cypress run -b chrome -s "**/*spec.j,baseUrl='<app_url>',username='<username>,password='<password>'`

# Test debugging:

## Local System

* During test execution locally if any test fails, screenshot with execution log will be taken for that. Screenshots will be available under the path: ```cypress-pipeline-demo/cypress/screenshots``` 

* Junit xml reports are created under the path: ```cypress-pipeline-demo/cypress/reports``` 

* By default capturing test videos is turned off by the ```cypress.json```. If needed, can be possible to turn it on there.if enabled the you can find videos under the path:```cypress-pipeline-demo/cypress/videos``` 

## Azure Pipeline
* Got to build artifacts for screenshots and videos

### Test Result

* Go to tests tab under pipeline for test results

![test result](/Tests_results.png)

## Supported browsers

- Chrome
- Firefox
- Edge

[Cypress browsers](https://docs.cypress.io/guides/guides/launching-browsers.html#Browsers)
