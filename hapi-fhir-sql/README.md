HAPI FHIR Server in Azure with SQL Backend
--------------------------------------------------------------

This template deploys the infrastructure for running the [HAPI FHIR](http://hapifhir.io/) example server in an Azure Web App with an Azure SQL Database backend. The Web App will be configured with all necessary connection strings, java versions, etc. 

After deploying the infratructure, you need to generate a `*.war` file for deployment:

* Install [Java SDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* Download [Apache Maven](https://maven.apache.org/download.cgi)
* [Install Maven](https://maven.apache.org/install)
* Get the source code and patch:
```bash
git clone https://github.com/jamesagnew/hapi-fhir.git
cd hapi-fhir

#Select the version you want, e.g.:
git checkout -b v3.4.0 v3.4.0

#Get and apply patch
wget https://raw.githubusercontent.com/hansenms/fhir-azure/master/hapi-fhir-sql/0001-Using-Azure-SQL.patch
git am 0001-Using-Azure-SQL.patch
```
* Build:
```bash
cd hapi-fhir-jpaserver-example
mvn package
```
* Copy the `hapi-fhir-jpaserver-example.war` (from the `target` folder) file to the `D:\home\site\wwwroot\webapps` folder of the Azure Web App (e.g., using the Kudu console)


After deployment visit the web app (e.g., `https://WEBSITENAME.azurewebsites.com/hapi-fhir-jpaserver-example/`) with a browser to make sure it is up and running.


<a href="https://transmogrify.azurewebsites.net/hapi-fhir-sql/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://transmogrify.azurewebsites.net/hapi-fhir-sql/azuredeploy.json?environment=gov" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
