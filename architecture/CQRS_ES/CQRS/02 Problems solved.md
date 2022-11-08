

The main goal which could be achieved by CQRS pattern is increasing of the system performance.
CQRS addresses the following points which influence on a system performance in general:
- Data modification and read queries can have much different workloads, although they are applied to the same database and service.
- Sometimes operation requires additional updates that are not related to just one table, ex. update of some client orders should be distributed across tables that serve the needs of diverse departments. More over, in some cases updates can affect a data which is even not related with business purporse of operation: during orders update we are "blocking" table with goods or logistics information.
- Extra concurrent access to the same columns during the queries execution.