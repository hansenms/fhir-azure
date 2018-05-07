Firely FHIR Servers on Azure
-----------------------------

[FHIR](hl7.org/fhir) Fast Healthcare Interoperability Resources – is a next generation standards framework created by HL7. It is used for transfer of clinical and administrative data between software applications used is by various healthcare providers. 

In this repository, you will find templates for setting up FHIR servers from [Firely](https://fire.ly) and [HAPI FHIR](http://hapifhir.io/).

Firely has the open source [Spark](https://github.com/FirelyTeam/spark) server, which supports Draft Standard for Trial Use 2 (DSTU2) and they also have a commercial server called [vonk](https://fire.ly/vonk), which supports Standard for Trial Use 3 (STU3). The servers and underlying libraries are written in .NET and can use MongoDb as a backend store. Vonk also supports SQL server as the backend store. 

[HAPI FHIR](http://hapifhir.io/) is a library for adding FHIR support to your applications. It is writtent in Java and licensed under the Apache Software License, version 2. The project includes an example server, which I have [modified](https://github.com/hansenms/hapi-fhir/tree/azuresql) to use Azure SQL as the backend database. 

The templates use all Platform as a Service (PaaS) services with [Azure Web App](https://azure.microsoft.com/en-us/services/app-service/web/) on the front end and either [Cosmos DB](https://azure.microsoft.com/en-us/services/cosmos-db/) (with MongoDb API) or [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/) on the backend. There are currently 3 templates to choose from:

* [Spark Server with backend Cosmos DB (MongoDb API)](spark/).
* [Vonk Server with CosmosDB (MongoDb API) backend](vonk-cosmosdb/).
* [Vonk Server with Azure SQL backend](vonk-sql/).
* [HAPI-FHIR Example Server with Azure SQL backend](hapi-fhir-sql/).

All templates automate the deployment of required resources. The Spark template also deploys the application code. 

The Vonk server deployment requires a couple of manual steps to download the application binaries and a trial license since this is a commercial product. See instructions for the individual templates. Please note that the deployment of Vonk server with SQL backend is the only configuration mentioned as supported in the [documentation for the Vonk server](https://simplifier.net/vonk). So if you are considering any of these deployments for production, start with that one. 

The HAPI FHIR Server needs a `*.war` file for deployment. Please [see instructions](hapi-fhir-sql/). 

