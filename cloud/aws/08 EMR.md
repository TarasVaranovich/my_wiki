<u>**Service purpose**</u> <br />
Amazon Elastic MapReduce (EMR) - managed cluster platform that simplifies
running big data frameworks, such as _Apache Hadoop_ and _Apache Spark_
on AWS to process and analyse vast amounts of data.

<u>**Service benefits**</u> <br />
* cost savings
* networking 
* security - cluster termination protection, encryption
* audit,
* ability to work with data lakes
* monitoring
* scaling *
* reliability - automatically replaces instances in case of failure,

<u>**Service limitations**</u> <br />
-//-

<u>**Programming languages**</u> <br />
Frameworks: Hadoop, Spark, Hive, Pig.
SDK is available on the  following languages: 
Go, Java, C#, VB.NET, Node.js, PHP, Python and Ruby.

<u>**Payment method**</u> <br />
Customers only pay for the resources they use.

<u>**Related services**</u> <br />
S3, DynamoDB, VPC, Cloud Watch, IAM, Cloud Trail, Data Pipeline, Lake Formation

<u>**Additional information**</u> <br />
EMR is bound with S3 by dint of VPC. <br />
It provides clusters with pre-installed software or just a raw linux system. <br />
It is feasible to use 3 file systems in EMR:<br />
* HDFS - Hadoop Distributed File System
* EMRFS - Elastic MapReduce FIle System. Based on HDFS. 
* The key difference is added extension which let HDFS to use S3 storage 
as a file system in cluster like HDFS.
* Local file system - refers to a locally connected disk.
For resource management applied YARN cluster resource manager

<span style="color: green">*TODO:// add references to related services*</span>