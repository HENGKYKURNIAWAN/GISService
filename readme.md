A Simple Service for Fetching List of Indonesian Provinces, Regencies, Sub-Districts and Villages.
===================

Updated (26 September 2015)
-------------------
Adding new Province, Regencies, Sub-Districts and Villages based on 2015 data. Now with a total of 34 Provinces, 514 Regencies, 7.042 Sub-Districts and 81.873 Villages.

Tools
-------------------
* Programming Language - Java
* IDE - Netbeans 7.2
* DB - MySQL
* Framework - Hibernate ORM - JaxWS 2.2
* Build Tool - Maven

How to Build
-------------------
1. Restore dbgis.sql into existing MySql database.
2. Make sure you have Internet Connection
3. Open project using Netbeans
4. Right click on your project, and build 
    (be patience, Maven will download libraries needed automatically)
5. Press F6 to Run your project
6. You will find your service on this url, http://localhost:8084/GISService/Service.

Messaging
--------------------
There are 4 requests provided, getProvinsis, getKabupatens, getKecamatans and getDesas. Messaging is done by using xml formats (webservice), and you could get this project's wsdl from  browser (http://localhost:8084/GISService/Service?wsdl) or from Service.wsdl file.

Here is the example of getProvinsis request.

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.gis.edw.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:getProvinsis/>
   </soapenv:Body>
</soapenv:Envelope>
```

and here is the response
```xml
<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">
   <S:Body>
      <ns2:getProvinsisResponse xmlns:ns2="http://service.gis.edw.com/">
         <return>
            <id>11</id>
            <nama>Aceh</nama>
         </return>     
		.....		 
		<return>
            <id>94</id>
            <nama>Papua</nama>
		</return>
      </ns2:getProvinsisResponse>
   </S:Body>
</S:Envelope>
```

Appreciations
--------------------
Provinces, Regencies, Sub-Districts and Villages datas are provided by kind permission from Panji09 (http://www.kaskus.co.id/thread/518298ae8227cf927f000003/sharedatabase-wilayah-indonesia) and from http://mfdonline.bps.go.id/.