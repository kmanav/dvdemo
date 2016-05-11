## JBoss Data Virtualization Simple Muti-Datasource Demo

This demo project deals with a simple scenario of two disparate data sources:
* US Customers database in MySQL, total \# of records 17 
* EU Customers database in Postgres, total \# of records 18

The view table __Customers.all_customers__ does a __UNION__ of these two tables and one can notice getting a total of 35 records back when the following query is run
```sql
select * from Customers.all_customers
```

###Prerequsites 
* JBoss Data Virtualization runtime (EAP 6.4 + JDV 6.2 combo) installed and patched (if any)
* JBoss Developer Studio 8.1.0.GA with [Integration Stack](http://tools.jboss.org/downloads/devstudio_is/luna/8.0.5.GA.html) and __JBoss Data Virtualization Development__ plugins installed 

###Setup

1. Import the project and open the project in Teiid Designer
2. Refer to the README.md document in the __drivers__ folder, download and save them in the same folder 
3. You may be prompted for password for both __US_Customers__ and __EU_Customers__, use `dvuser` as the password in each case
4. Right-click on the `dvdemo.vdb` and choose __Modeling → Execute__ to push the drivers and setup the datasources on the JDV runtime
5. For any further changes to the models, _resynchronize_ the contents in the __dvdemo.vdb__ and __Execute__ the VDB for testing

> __Note:__ Since the project does not contain relevant database connection profiles (those which typically exist in the workspace) that can be reused to **preview** the individual source tables, it is important to first run the step #4 in the above list to be able to push the JDBC drivers to the running JDV runtime before planning on previewing the source tables. 
