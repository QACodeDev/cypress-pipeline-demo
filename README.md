# Cypress E2E testing with Azure CI/CD pipeline 
This is a project which you can use to start your E2E testing with Cypress by azure CI/CD.

- Parallel execution
- Cross Browser Testing
Cypress Demo

###Cypress version : 4.5.0

# Installation  
1. Create a project directory and Clone the project: 
```git clone https://github.com/QACodeDev/cypress-pipeline-demo.git``` 
2. Under the project directory install the followings: 
```npm install```

# How to start

In order to start using this project. You will have to do the following steps:

 Provide the `username`, `password`, and `baseUrl` in cypress.json and put other required test data.

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
* Alternative command : `$(npm bin)/cypress run -b chrome -s "**/*spec.js" ,baseUrl='<app_url>',username='<username>,password='<password>'`

# Test debugging:
##Locally
* During test execution locally if any test fails, screenshot with execution log will be taken for that. Screenshots will be available under the path: ```cypress-pipeline-demo/cypress/screenshots``` 
*Junit xml reports are created under the path: ```cypress-pipeline-demo/cypress/reports``` 
* By default capturing test videos is turned off by the ```cypress.json```. If needed, can be possible to turn it on there.if enabled the you can find videos under the path:```cypress-pipeline-demo/cypress/videos``` 
##Azure Pipeline
* Got to build artifacts for screenshots and videos

## Supported browsers

- Chrome
- Firefox
- Edge

[Cypress browsers](https://docs.cypress.io/guides/guides/launching-browsers.html#Browsers)
