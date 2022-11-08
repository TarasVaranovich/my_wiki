           

Solution:

*Materialized data view* pattern represents a separated adopted cache which contains data in convenient readable format. Cache never updated directly. Its update can be initialized using a scheduled task, an external trigger (automatically by trigger), or a manual action to regenerate the view. Cache should be changed when original storage was updated and system detects this changes.
Materialized view can be speed up by indexing of tables in RDBMS or using specific solutions like Apache Hadoop, Spark, AWS, MS Azure etc..,

Let consider simplified example which help to explain the pattern salt.
We have department hierarchy stored in company locally. Additionally, we have incomes information stored in different banks. Our company is cosmopolite and our team mates lives in different countries and pay different taxes. That's why we have some access to the CIA database as a well :)
All storages are located in different datacenters. And department database has graph structure which is not convenient for some kind of queries.
Our task is to get on-hand information about brutto and netto salaries in group under employee 2.
It's not surprise each attempt to query required information takes pretty long time.
The decision to hold it in cache and update on demand is more elegant.

![[Materialized_data_view_03.png]]