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
* Import the project and open the project in Teiid Designer
* You may be prompted for password for both __US_Customers__ and __EU_Customers__, use `dvuser` as the password in each case
* For any changes to the models, _resynchronize_ the contents in the __dvdemo.vdb__ and (right-click) __Execute__ the VDB when testing
