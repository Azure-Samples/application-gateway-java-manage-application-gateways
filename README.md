---
page_type: sample
languages:
- java
products:
- azure
extensions:
  services: Network
  platforms: java
---

# Getting Started with Network - Manage Application Gateway - in Java #


  Azure network sample for managing application gateways.
  <p>
  - CREATE an application gateway for load balancing
  HTTP/HTTPS requests to backend server pools of virtual machines
  <p>
  This application gateway serves traffic for multiple
  domain names
  <p>
  Routing Rule 1
  Hostname 1 = None
  Backend server pool 1 = 4 virtual machines with IP addresses
  Backend server pool 1 settings = HTTP:8080
  Front end port 1 = HTTP:80
  Listener 1 = HTTP
  Routing rule 1 = HTTP listener 1 =&gt; backend server pool 1
  (round-robin load distribution)
  <p>
  Routing Rule 2
  Hostname 2 = None
  Backend server pool 2 = 4 virtual machines with IP addresses
  Backend server pool 2 settings = HTTP:8080
  Front end port 2 = HTTPS:443
  Listener 2 = HTTPS
  Routing rule 2 = HTTPS listener 2 =&gt; backend server pool 2
  (round-robin load distribution)
  <p>
  - MODIFY the application gateway - re-configure the Routing Rule 1 for SSL offload and
  add a host name, www.contoso.com
  <p>
  Change listener 1 from HTTP to HTTPS
  Add SSL certificate to the listener
  Update front end port 1 to HTTPS:1443
  Add a host name, www.contoso.com
  Enable cookie-based affinity
  <p>
  Modified Routing Rule 1
  Hostname 1 = www.contoso.com
  Backend server pool 1 = 4 virtual machines with IP addresses
  Backend server pool 1 settings = HTTP:8080
  Front end port 1 = HTTPS:1443
  Listener 1 = HTTPS
  Routing rule 1 = HTTPS listener 1 =&gt; backend server pool 1
  (round-robin load distribution)
 

## Running this Sample ##

To run this sample:

See [DefaultAzureCredential](https://github.com/Azure/azure-sdk-for-java/tree/master/sdk/identity/azure-identity#defaultazurecredential) and prepare the authentication works best for you. For more details on authentication, please refer to [AUTH.md](https://github.com/Azure/azure-sdk-for-java/blob/master/sdk/resourcemanager/docs/AUTH.md).

    git clone https://github.com/Azure-Samples/application-gateway-java-manage-application-gateways.git

    cd application-gateway-java-manage-application-gateways

    mvn clean compile exec:java

## More information ##

For general documentation as well as quickstarts on how to use Azure Management Libraries for Java, please see [here](https://aka.ms/azsdk/java/mgmt).

Start to develop applications with Java on Azure [here](http://azure.com/java).

If you don't have a Microsoft Azure subscription you can get a FREE trial account [here](http://go.microsoft.com/fwlink/?LinkId=330212).

---

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.