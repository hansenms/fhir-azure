Firely Spark (open source) FHIR Server in Azure
------------------------------------------------

This template deploys the [Firely Spark FHIR server](https://github.com/FirelyTeam/spark) with an Azure Cosmos DB (MongoDb API) backend. Please note because of 1) certain TLS requirements of Cosmos DB and 2) Spark's use of direct to filesystem logging, it deploys a modified version of the Spark code, which can be found in my [dstu2/azure branch of the Spark repo](https://github.com/hansenms/spark/tree/dstu2/azure). You can [compare](https://github.com/FirelyTeam/spark/compare/dstu2/master...hansenms:dstu2/azure) to see the specific changes made from the dstu2/master branch.

<a href="https://transmogrify.azurewebsites.net/spark/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://transmogrify.azurewebsites.net/spark/azuredeploy.json?environment=gov" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
