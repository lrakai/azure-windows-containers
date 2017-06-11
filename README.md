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
Connect to the VM and get containerizing! The artifacts are loaded onto the temporary D: drive to exploit the SSD of the Standard A1 V2 VM type.
