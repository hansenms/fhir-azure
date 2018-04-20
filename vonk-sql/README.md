Firely Vonk (commercial) FHIR Server in Azure with SQL Backend
--------------------------------------------------------------

This template deploys the infrastructure for running the [Firely Vonk](https://fire.ly/vonk) FHIR servce in an Azure Web App with an Azure SQL Database backend. The Web App will be configured with all necessary connection strings, etc. 

After deploying the infratructure, you need to download the binaries from [https://simplifier.net/vonk](https://simplifier.net/vonk). You will need to register. This is also where you can get a trial license if you don't have a license already. 

The file with the binaries is called `vonk_distribution.zip` and you can add your trial license to the package by simply dragging and dropping it onto the zip file. After adding the license file, go to the Kudu console of the deployed web app and use "Zip Deploy" from the tools menu to deploy the application. 

After deployment visit the web app with a browser to make sure it is up and running. You can get interact with the Vonk server, e.g.:

```

```

<a href="https://transmogrify.azurewebsites.net/vonk-sql/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://transmogrify.azurewebsites.net/vonk-sql/azuredeploy.json?environment=gov" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
