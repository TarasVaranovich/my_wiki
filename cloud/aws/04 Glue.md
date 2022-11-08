<u>**Service purpose**</u> <br />
AWS Glue - is a **_serverless_** service responsible for discover,
prepare, move and integrate data.

<u>**Service benefits**</u> <br />
* building data pipeline with a single integration service
* serverless and low cost
* various methods to build pipelines (drag & drop etc..)
* various data processing methods

<u>**Service limitations**</u> <br />
-//-

<u>**Programming languages**</u> <br />
Code-free jobs running. <br />
API are available in various programming languages: <br />
C++, Go, Java, JavaScript, Kotlin, .NET, Node.js, PHP, Python, Rust, Swift.

<u>**Payment method**</u> <br />
For crawlers and ETL jobs - hourly rate billed per second.
For Data Catalog monthly fee storing and accessing metadata.
For DataBrew billed sessions per session and jobs billed per minute.
Crawlers billed per DPU-Hour

<u>**Related services**</u> <br />
S3, Redshift, CloudWatch, RDS, Athena, EMR, QuickSight, Kinesis, MSK,
SageMaker, Lake Formation

<u>**Additional information**</u> <br />
Running ETL jobs as a new data arrives (event-driven).
Glue load transformed data into target data store as Redshift or S3.
Process is monitored and logged.

Crawlers - single data processing unit (DPU) provides 4vCPU and 16 GB memory. 