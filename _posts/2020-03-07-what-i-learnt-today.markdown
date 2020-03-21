---
layout: post
title:  "What I Learnt Today - Azure Containers"
date:   2020-03-07 09:00:00 +0000
categories: updates azure
---
## Azure Containers
This is how to run a container using the Azure Container Instance (ACI) service. It is not using Kubernetes (AKS). I'll get to that later

### Install the Azure CLI
If you rather have the Azure CLI installed on your desktop instead of using the CLI built into the Azure Portal then download it from the Azure site. Its available in Windows, MacOS, Linux (in apt, yum, zypper, or script variants)

[Azure CLI download](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

##### Key AZ CLI Commands from the Quickstart tutorial 
| Command | Notes |
|---|---|
| `az login` | Logs the cli into your AZ account. It will launch a browser window where you will log in. If you have set your account to use an authenticator app such as the [Microsoft Authenticator App](https://www.microsoft.com/en-gb/p/microsoft-authenticator/9nblgggzmcj6?activetab=pivot:overviewtab) then you'll be asked to approve. Once you've done that, the CLI will log into your chosen Azure subscription |
| `az group create --name myResourceGroup --location uksouth`| Creates a new resource group in your subscription |
| `az container create --resource-group myResourceGroup --name mycontainer --image mcr.microsoft.com/azuredocs/aci-helloworld --dns-name-label aci-demo --ports 80` | Deploys the _aci-helloworld_ image as a container. |
| `az container show --resource-group myResourceGroup --name mycontainer --query "{FQDN:ipAddress.fqdn,ProvisioningState:provisioningState}" --out table` | When you run the command, the container's fully qualified domain name (FQDN) and its provisioning state are displayed. _Read the [ACI Quickstart](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-quickstart) for more information about how this works_ |
| `az container logs --resource-group myResourceGroup --name mycontainer`| Tails the container logs|
| `az container attach --resource-group myResourceGroup --name mycontainer`| Shows the `stdout` and `stderr` streams from your container|
| `az container list --resource-group myResourceGroup --output table` | lists the running containers|
| `az container delete --resource-group myResourceGroup --name mycontainer`|  Deletes the containter from your resource group |
| `az group delete --name myResourceGroup`|Deletes the resource group and any associated resources in it. Use this to clean up your supscription and remove any associate charges|

### 30 Minute AZ Quickstart
Follow the steps in the [ACI Quickstart](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-quickstart)  As you've just installed the AZ CLI, use it as an exercise to get started with the Azure Command Line Interface (CLI). It will be where you spend more of your time as you continue to develop your Azure skills.

If you follow the instructions correctly, you'll end up with a simple container running a website that displays an image:

![Azure Image](/assets/images/view-an-application-running-in-an-azure-container-instance.png)

For bonus points, do all three Quickstarts and learn how to create resource groups using the Portal (point and click), CLI, or Powershell*

### What's next
The Quickstart only scratches the surface of ACI, and if you want to know how create a container from scratch and then deploy it using ACI, then you need to follow the [Azure Container Instances tutorial](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-tutorial-prepare-app)

This is a far more in-depth, 3 part tutorial that covers:

* Creating a local container image
* Creating a an Azure Container Registry
* Creating a Service Principal and Password
* Deploying your container 

Then there are further tutorials for deploying a multi-container group and integrating them with services such as Azure Functions

##### Installing the AZ PowerShell module
\* _Note that the PowerShell Container tutorial will also need you to install the_ [Azure PowerShell module](https://docs.microsoft.com/en-gb/powershell/azure/install-az-ps?view=azps-3.5.0&viewFallbackFrom=azps-3.3.0)

* _From a Powershell prompt (_not a cmd prompt_ )

`Install-Module -Name AZ -AllowClobber -Scope CurrentUser`

and follow the prompts.  When it has finished installing, type `Connect-AzAccount` and a browser window will open to ask you to login in to Azure. Once you've done that, the Connect command will complete showing your account and subscription.

