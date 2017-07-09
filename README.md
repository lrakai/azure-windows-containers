# azure-windows-containers
ARM template to start a Windows VM and provision it with artifacts to containerize. Azure's Windows Server 2016 with Containers VM image is used for its convenience in having the [microsoft/windowsservercore](https://hub.docker.com/r/microsoft/windowsservercore/) and [microsoft/nanoserver](https://hub.docker.com/r/microsoft/nanoserver/) images ready to use. That avoids 6GiB of download.

# Included Artifacts
The project contains a [python project](https://github.com/lrakai/flask-content-advisor) and published artifacts from an [ASP.NET MVC project](https://github.com/lrakai/aspnet-docker-app). Both include a Dockerfile in their directory.

# Usage
Any method of deploying an ARM template will do. For example, using `Powershell`, login to your Azure account
```ps1
Login-AzureRmAccount
```
then issue
```
New-AzureRmResourceGroup -Name Dockering -Location "Central US"
New-AzureRmResourceGroupDeployment -Name WindowsContainers -ResourceGroupName Dockering -TemplateFile .\arm-template.json
```
Or by using the one-click deploy button below:
Alternatively, you can perform a one-click deploy with the following button:
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Flrakai%2Fazure-windows-containers%2Fmaster%2Finfrastructure%2Farm-template.json">
    <img src="https://camo.githubusercontent.com/9285dd3998997a0835869065bb15e5d500475034/687474703a2f2f617a7572656465706c6f792e6e65742f6465706c6f79627574746f6e2e706e67" data-canonical-src="http://azuredeploy.net/deploybutton.png" style="max-width:100%;">
</a>

Connect to the VM and get containerizing! The artifacts are loaded onto the temporary D: drive to exploit the SSD of the Standard A1 V2 VM type.
