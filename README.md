# Fabric-IaC

<img src="images/Fabric_256.svg" alt="Fabric Image" style="margin: 10px;" width="100" align="right"/>

![level](https://img.shields.io/badge/Microsoft%20Fabric-IaC-green)

## Introduction

This repo will create a resource group, an F2 **Fabric Capacity** and a **Logic App** to pause the Fabric Capacity in the UK South region.  Use the [Deploy to Azure](#deploy-to-azure) button to set the parameters incuding location, Fabric SKU and object names.

![Fabric IaC](images/fabriciac.png)

The code has been built with external subscriptions in mind but could be adapted for any Azure subscription.

## Deploy to Azure
Press this button to set the parameters and deploy to an Azure subscription.

> [!TIP]
> Open the repo in an Edge (or Chrome) Profile for your external subscription to make sure you deploy to that subscription

### Parameters

The Bicep template has the following parameters:


| Parameter            | Description                                                                                       | Example Value                      |
|----------------------|---------------------------------------------------------------------------------------------------|------------------------------------|
| adminEmail  | The admin email for the subscription.  This is required to authorise the API connection                                                              | admin999@MCAPSetc.onmicrosoft.com  |
| baseName             | the base name of the resources, eg if the baseName is `general-uks` the resources created will be: `rg-general-uks`, `fabgeneraluks`, `logicApp-pause-fabgeneraluks` | general-uks                        |
| location             | the selected Azure region for deployment, eg `UKSouth`                                            | UKSouth                            |
| hour                 | the approximate hour the Fabric capacity will be paused, eg 21 for 9pm.  Tweak the Logic App once deployed if you need a more specific time                                                                                             | 21                                 |
| sku                  | this is the Fabric SKU, eg `F2`. Suggest leaving it at `F2` and manually scale in the portal if required | F2                                 |


Click the button below when ready:

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/DamOConnor/fabric-iac-dta/refs/heads/main/arm/main.json)
