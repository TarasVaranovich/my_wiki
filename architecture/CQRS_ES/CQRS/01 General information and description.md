
**CQRS pattern** – command query responsibility segregation

Historically the base for the CQRS pattern was the CQS pattern.
CQS – command-query-separation
- queries return results but don’t mutate the state of the system
- commands(modifiers) mutate the state of the system

In other words, *create, update and delete* operations are considered to be commands since they mutate state. Hence *read* operation is a query since it wil never mutate state. In general any method which mutates state must be a command and any method which never mutates state must be a query. In canonical undersanding *commands* shouldn't return any business data except command execution resut as it is.

Shortly CQS pattern states : “Ask a question shouldn’t modify result”.
The main idea of the CQS pattern is performing writes separate from reads.
Additionally nowadays it tightly coupled with the functional programming philosophy:
state modification (any command application) in details implemented by applying <u>immutable</u> event.

CQRS (Command Query Responsibility Segregation) is an evolutional extension of CQS. The main difference is availability of separate models and data stores in CQRS unlike in CQS the same data store used for both commands and queries. The data between data stores is usually synchronized using a service bus.