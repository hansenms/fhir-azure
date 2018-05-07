HAPI FHIR Server in Azure with SQL Backend
--------------------------------------------------------------

This template deploys the infrastructure for running the [HAPI FHIR](http://hapifhir.io/) example server in an Azure Web App with an Azure SQL Database backend. The Web App will be configured with all necessary connection strings, java versions, etc. 

After deploying the infratructure, you need to generate a `*.war` file for deployment:

* Install [Java SDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* Download [Apache Maven](https://maven.apache.org/download.cgi)
* [Install Maven](https://maven.apache.org/install)
* Get the source code:
```
git clone https://github.com/hansenms/hapi-fhir.git
cd hapi-fhir
git checkout azuresql
cd hapi-fhir-jpaserver-example
```
* Build:
```
mvn install
```
* Copy the `hapi-fhir-jpaserver-example.war` (from the `target` folder) file to the `D:\home\site\wwwroot\webapps` folder of the Azure Web App (e.g., using the Kudu console)


After deployment visit the web app (e.g., `https://WEBSITENAME.azurewebsites.com/hapi-fhir-jpaserver-example/`) with a browser to make sure it is up and running.


<a href="https://transmogrify.azurewebsites.net/vonk-sql/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://transmogrify.azurewebsites.net/vonk-sql/azuredeploy.json?environment=gov" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
