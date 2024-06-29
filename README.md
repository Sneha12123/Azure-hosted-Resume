
# Azure-hosted-Resume

This project showcases my Resume built using HTML, CSS, and JavaScript for the frontend, and C# for the backend. Which is entirely hosted on a serverless database, Azure CosmosDB. The project includes Azure Functions that serve as API endpoints to handle various backend tasks. The website is deployed on Azure and is continuously updated via the CI/CD pipeline.

This project is a part of The Cloud Resume Challenge
https://cloudresumechallenge.dev/docs/the-challenge/azure/



## Deployment

To view the Resume visit 
https://azureresumestoragest.z20.web.core.windows.net/

How to Run Locally

- After cloning the project navigate to the frontend directory and open index.html in your browser to view the resume.
- Set up and run the backend functions locally using C# development environment.
- Ensure you have Azure Functions Core Tools installed. 

## API Endpoint

API Endpoints
The project includes Azure Functions that serve as API endpoints to handle various backend tasks. For example:

- GetResumeCounter: An endpoint to get the current visit count for the resume, with data stored in Azure Cosmos DB.

To deploy Resume counter run

cd to backend\api> func host start

Functions:

        GetResumeCounter: [GET,POST] http://localhost:7071/api/GetResumeCounter

Response 

{
  "id": "1",
  "count": 97
}

## Screenshots

![homepage](https://github.com/Sneha12123/Azure-hosted-Resume/assets/103009587/0ca097f2-d02a-4f11-8d81-47799de2a712)

![aboutme](https://github.com/Sneha12123/Azure-hosted-Resume/assets/103009587/e7b681f1-19ac-4ef5-bc4f-345eb564e426)

![resume](https://github.com/Sneha12123/Azure-hosted-Resume/assets/103009587/f23e1e93-1f20-4a5f-a10e-b92e32cd92d3)

![aboutme2](https://github.com/Sneha12123/Azure-hosted-Resume/assets/103009587/c0c4be52-791b-400c-885a-f08633747cfa)


## Azure Services used

Signup to https://azure.microsoft.com/en-in/get-started/azure-portal

1. Azure Resources
Various Azure resources are utilized to ensure the scalability, reliability, and security of the website.

2. Azure Functions
Serverless compute service used to execute backend code in response to HTTP requests. It's used for functionalities like fetching the visit count for the resume.

3. Azure Blob Storage 
Used to store and manage the website's data and assets.

4. Azure CosmosDB
A fully managed NoSQL database service used to store and retrieve data such as the visit count for the resume. It ensures low latency and high availability.

## Building process

1. Building Frontend 
- Create HTML & CSS file for the static Resume
- Create main.js file containing counter data

2. Building Backend
- Setting up Azure CosmosDB, container, data
- Setting up Azure Functions to interact with CosmosDB, using C# and .NET core as runtime. (you can execute the GetResumeCounter function)
```bash
  func host start
```
- Install the NuGet package for .NET CLI
https://www.nuget.org/packages/Microsoft.Azure.Functions.Worker.Extensions.CosmosDB/

- Configure CORS settings in local.settings.json

3. Deploying to Azure
- Deploy Azure Functions to Azure grab it's URL and update in JS file
- Deploy static website to blob storage in Azure

4. Bulding CI/CD pipeline
- Create frontend & backend workflow in github
- perform unit test

5. Testing 
- Navigate to Tests folder and and create test template, run 
```bash
  dotnet new xunit
```
add package
```bash
  dotnet add package Microsoft.AspNetCore.Mvc
```
to create reference to Functions
```bash
  dotnet add reference ../api/api.csproj
```
implement unit test on TestCounter.cs 
```bash
  dotnet test
```

## Documentation

Frontend
- How to make an API call with JavaScript and in a simple way how to use it to make an API call 
https://www.digitalocean.com/community/tutorials/how-to-use-the-javascript-fetch-api-to-get-data

Backend

The back-end is an HTTP triggered Azure Functions with Cosmos DB input and output binding. The Function is triggered, it retrieves the CosmosDB item, add +1 to it, and saves it and returns its value to the caller. 

- HTTP triggered Azure Functions https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-http-webhook-trigger?tabs=python-v2%2Cisolated-process%2Cnodejs-v4%2Cfunctionsv2&pivots=programming-language-csharp

- Create a Cosmos DB account via the portal https://learn.microsoft.com/en-us/azure/cosmos-db/nosql/quickstart-portal
 
- Create an HTTP triggered Azure Function in Visual Studio Code https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v4%2Cpython-v2%2Cisolated-process&pivots=programming-language-csharp

- Azure Functions Cosmos DB bindings https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-cosmosdb-v2?tabs=isolated-process%2Cextensionv4&pivots=programming-language-csharp

- Enable CORS with Azure Functions locally https://learn.microsoft.com/en-us/azure/azure-functions/functions-how-to-use-azure-function-app-settings?tabs=portal%2Cto-premium#cors

Testing Resources 

https://xunit.net/docs/getting-started/netcore/cmdline

CI/CD Resources 
- How to deploy a blob storage static site with GitHub actions https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-static-site-github-actions?tabs=userlevel

## 🛠 Skills
- HTML, CSS, Javascript 
- C#
- Azure cloud and services
- Git & Github Actions
- CI/CD pipelines
- Unit testing 





