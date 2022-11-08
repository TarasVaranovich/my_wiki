The main tactic points of CQRS implementation:
- on the update side the various combinations of data is restricted
- the different data models – for reading and for modification
- move validation to update side
- \* commands are task-based and support asynchronous processing(queue)
- queries never modify database and contain any domain knowledges
- synchronization is provided by publishing event from write DB to read DB (in case of separate databases)
- separate load-balancing because read store in more cases has higher workload


![[CQRS_05.png]]

          
Pattern uses for communication between data models collective in-memory database in case of models are on the same machine. If data models are distributed to different services for replication used messaging. Avoidence of possible merge-conflicts between replicas achieved by *eventual consistency* and *conflict-free replicated data types*.

\* - be sure commands have to be applied in right chronological order in the same context. Asynchronous processing implies parallel applying of unrelated commands.