---
title: Deep Dive Azure Extensions in Visual Studio Code
subtitle: A interesting tale about function of design
excerpt: >-
  hassle-free way to set up deployments using some built-in Extensions for Visual Studio Code (VSC)
date: '2019-02-26'
thumb_image: images/azure1.jpg
thumb_image_alt: White concrete building wall
image: images/azure1.jpg
image_alt: White concrete building wall
seo:
  title: Deep Dive Azure Extensions in Visual Studio Code
  description: >-
    hassle-free way to set up deployments using some built-in Extensions for Visual Studio Code (VSC)
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Deep Dive Azure Extensions in Visual Studio Code
      keyName: property
    - name: 'og:description'
      value: >-
        hassle-free way to set up deployments using some built-in Extensions for Visual Studio Code (VSC)
      keyName: property
    - name: 'og:image'
      value: images/azure1.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Deep Dive Azure Extensions in Visual Studio Code
    - name: 'twitter:description'
      value: >-
        hassle-free way to set up deployments using some built-in Extensions for Visual Studio Code (VSC)
    - name: 'twitter:image'
      value: images/azure1.jpg
      relativeUrl: true
layout: post
---

Getting to know Visual Studio Code better over the last couple of years lead me down some new and interesting learning paths when it comes to finding ways to deploy web applications, UI and other front-end related items hassle-free.

Coming from Visual Studio 2015 and before that Eclipse, I was used to having my IDE do most, if not all, of the work when it comes to the running of a CI/CD pipeline. Thankfully those dev-shops having already setup environments/configs allowed me hassle-free on-boarding and deployments. The senior and principle developers already had a tried and tested workflow to follow and making sure other developers followed it was important.

Now that I've started to look into doing more full-stack work for my own projects I wanted an easy, hassle-free way to set up deployments using some built-in Extensions for Visual Studio Code (VSC) to achieve the same feel and flow like in those dev-shops of projects past.

The Microsoft Azure extensions for VSC along with Microsoft's free Azure offering for new devs ($200USD credit and free tiers in the USA) made it the perfect opportunity for trying out. Just make sure to [stick with the free tier](https://azure.com/e/0b85c8efd3f744488c636e0e9c04fa0f)when deploying apps - otherwise Azure will burn through that $200 fast!

If you're unfamiliar with Azure's roster of products, [here is the comparison between Azure and AWS](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services) and [between Azure and Google Cloud](https://cloud.google.com/free/docs/map-azure-google-cloud-platform). This helped me learn the equivalent service from one to the other.

## Azure Extensions List

This was going to be a long list of extensions but the Azure Tools extension coupled with Azure Repos and Azure Pipelines does the heavy lifting you'll need and uses other azure extensions to facilitate various aspects of the features mentioned.

### [Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

Get web site hosting, SQL and MongoDB data, Docker Containers, Serverless Functions and more, all on Azure, all from VS Code, in this one extension from Microsoft.

This is a must have that replaces several individual Azure extensions and adds the Azure Explorer inside Visual Studio Code. This lets you easily navigate around your Azure portal resources and can manage most items right here.

[![Azure Tooling for Visual Studio Code](images/explorer.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--sLQbBfjs--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://github.com/microsoft/vscode-node-azure-pack/raw/master/explorer.png)

- [The Azure App Service extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azureappservice) lets you quickly create sites, deploy them, view logs, and even set environment variables (such as a Connection String), right from within VS Code.

[![Azure Commands Palette](images/commandpalette.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--MoTEmBWx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://github.com/microsoft/vscode-node-azure-pack/raw/master/commandpalette.png)

- [VS Code's Cosmos DB support](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) lets you create and manage databases as well as write MongoDB command scripts in a scrapbook, with rich completions (IntelliSense) just as if you were writing JavaScript, Python, or C#.
- If you use SQL Server or Azure SQL Databases to store data for your applications, the [SQL Server extension](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql) enables SQL database connectivity directly within VS Code. With handy commands for connecting to database servers or instances, in-editor query results views, and IntelliSense completion for SQL, you'll be able to validate your code is manipulating your data properly without leaving VS Code.
- Have a static site you want to host? You can use [Azure Storage](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestorage) to host your site quickly and inexpensively. The Storage service also provides massive scale blob, file, and document storage with low latency and high throughput. VS Code's Storage support lets you deploy static sites, browse and edit Blob Containers, File Shares, Tables, and Queues.
- Store your Docker images in private Container Registries using the [Azure Container Registry](https://marketplace.visualstudio.com/items?itemName=formulahendry.docker-explorer), and run them in the cloud using App Service. VS Code's support for Docker helps you author Dockerfile and docker-compose files with rich completions (IntelliSense), syntax highlighting and checking, and linting support. The Explorer view makes it easy to build, run, and manage your local and remote containers and images.
- The [Azure CLI extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.azurecli) makes it easy to manage all of your Azure resources from a terminal. If you write CLI scripts, VS Code's support provides syntax highlighting and completions (IntelliSense) for the CLI commands as well as your resources in Azure. You can execute one or more commands and even see the results in richly formatted JSON, document.
- You can also automate the management of Azure resources using [Azure Resource Manager ("ARM") templates](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools). VS Code's support for ARM makes it easy to author these JSON documents with rich editing and navigation experiences for deployment templates and template language expressions, including completions (IntelliSense) for TLE function names, parameter references, signature help, Go to Definition, Peek Definition, and Find All References (Shift+F12) as well as Errors and Warnings.
- Develop and connect your IoT applications to Azure using the [Azure IoT Toolkit](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-toolkit). With this extension, you can interact with an Azure IoT Hub, manage connected devices, and generate code for your Azure IoT applications.

### [Azure Pipelines](https://marketplace.visualstudio.com/items?itemName=ms-azure-devops.azure-pipelines)

This is a small extension that is critical for me when automating front-end deployments. Basic YAML validation is built into VS Code, but now you can have syntax highlighting that's aware of the Pipelines YAML schema. This means that you get red squigglies if you say `tasks:` where you meant `task:`. IntelliSense is also schema-aware.

### [Azure Repos](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team)

[![Azure Repo Command Palette](images/vscode.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--DCIKQFXf--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://github.com/Microsoft/azure-repos-vscode/raw/master/assets/vscode.png)

This extension allows you to connect to Azure DevOps Services and Team Foundation Server and provides support for Team Foundation Version Control (TFVC). It allows you to monitor your builds and manage your pull requests and work items for your TFVC or Git source repositories.

#### Wrapping Up

So there you have it, with these 3 extensions you can gain pretty good coverage over the most used Azure services to quickly and easily deploy your applications. In another post, we'll deep dive into how to lift a local application to become a production-ready Web Application.

Use different Azure extensions, or got some tips and tricks to using the ones I mentioned above? Let me and others know in the comments!

Originally posted on [dev.to](https://dev.to/vip3rousmango/deep-dive-visual-studio-code---azure-extensions-2b9o)
