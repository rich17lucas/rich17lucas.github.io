---
layout: post
title:  "What I Learnt Today - Azure Containers"
date:   2020-03-07 09:00:00 +0000
categories: updates azure
---
## Azure Containers

### Install the Azure CLI
If you rather have the Azure CLI installed on your desktop instead of using the CLI built into the Azure Portal then download it from the Azure site. Its available in Windows, MacOS, Linux (in apt, yum, zypper, or script variants)

[Azure CLI download](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)


### 30 Minute AZ Quickstart
Follow the steps in the [ACI Quickstart](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-quickstart)  As you've just installed the AZ CLI, use it as an exercise to get started with the Azure Command Line Interface (CLI). It will be where you spend more of your time as you continue to develop your Azure skills.

If you follow the instructions correctly, you'll end up with a simple container running a website that displays an image:

![Azure Image](/assets\images\view-an-application-running-in-an-azure-container-instance.png)

For bonus points, do all three Quickstarts and learn how to create resource groups using the Portal (point and click), CLI, or Powershell*


##### Installing the AZ PowerShell module
\* _Note that the PowerShell Container tutorial will also need you to install the_ [Azure PowerShell module](https://docs.microsoft.com/en-gb/powershell/azure/install-az-ps?view=azps-3.5.0&viewFallbackFrom=azps-3.3.0)

* _From a Powershell prompt (_not a cmd prompt_ )

`Install-Module -Name AZ -AllowClobber -Scope CurrentUser`

and follow the prompts.  When it has finished installing, type `Connect-AzAccount` and a browser window will open to ask you to login in to Azure. Once you've done that, the Connect command will complete showing your account and subscription.