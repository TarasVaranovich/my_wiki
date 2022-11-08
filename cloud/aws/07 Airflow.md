<u>**Service purpose**</u> <br />
Amazon Managed Workflows for Apache Airflow (MWAA) - 
orchestrates workflows using Direct Acyclic Graphs (DAGs) written in Python.
DAGs written before a deployed into S3 bucket. DAG is a graph of runned tasks.
MWAA is used for running ETL jobs, ML Pipelines and managed DevOps tasks.

<u>**Service benefits**</u> <br />
The benefits compare to Airflow by itself are automoted setup, scaling, 
security, encryption, upgrades and monitoring.

<u>**Service limitations**</u> <br />
-//-<br />

<u>**Programming languages**</u> <br />
Python

<u>**Payment method**</u> <br />
-//-<br />

<u>**Related services**</u> <br />
S3, Amazon Cloud Watch

<u>**Additional information**</u> <br />

**Origin**<br />
Based on open-source Apache Airflow project.
Pushes execution logs into Amazon Cloud Watch.
It is possible to just download and use Apache Airflow.
DAGs can be used on defined schedule (e.g. hourly and daily) or
based on external event triggers.<br />
*Cloud compressor is managed version of Airflow on GCP*.

**Under the hood**<br />
Worker - is an instance which receives task from queue and responsible for its execution.<br />
Execution node - is a machine on which task will be executed.
Workers are assigned to nodes.<br />
Each task is assigned to the *queue* (RabbitMQ). Workers are listen queues
and execute pulled out tasks. <br />
Execution metadata is stored in MySQL database.<br />
Worker imports execution plans from DAGs folder.
Ordinarily DAGs folder is stored in GIT repository and synced across machines
using Chef, Puppet, Ansible etc.
Should be provided database backend to store execution results.

<span style="color: green">*TODO:// add references to related services*</span>