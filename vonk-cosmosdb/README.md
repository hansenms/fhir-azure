Firely Vonk (commercial) FHIR Server in Azure with Cosmos DB Backend
---------------------------------------------------------------------

This template deploys the infrastructure for running the [Firely Vonk](https://fire.ly/vonk) FHIR servce in an Azure Web App with an Azure Cosmos DB (MongoDb API) backend. The Web App will be configured with all necessary connection strings, etc. 

*NOTE* This configuration is not considered supported as per the Vonk documentation and should be considered for experimentation purposes only.

After deploying the infratructure, you need to download the binaries from [https://simplifier.net/vonk](https://simplifier.net/vonk). You will need to register. This is also where you can get a trial license if you don't have a license already. 

The file with the binaries is called `vonk_distribution.zip` and you can add your trial license to the package by simply dragging and dropping it onto the zip file. After adding the license file, go to the Kudu console of the deployed web app and use "Zip Push Deploy" from the tools menu to deploy the application. 

After deployment visit the web app with a browser to make sure it is up and running. You can get interact with the Vonk server, e.g.:

```
GET https://<FHIR SERVER NAME>.azurewebsites.<us or net>/metadata
```

If you would like to load some test data to the Vonk server, I have some [notes on how to do that](../data-preload/).

<a href="https://transmogrify.azurewebsites.net/vonk-cosmosdb/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://transmogrify.azurewebsites.net/vonk-cosmosdb/azuredeploy.json?environment=gov" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
