#### Before start to implement CQRS highly recommended to acquaint with "domain language":

<u>*Command*</u> - is a class which performs an action, modifies data and optionally can return result. Hence command containing property required to mutate data.

<u>*Query*</u> -  is a class which returns data to the caller without side effects. Hence query containing properties required to retreive data from a data store.

<u>*Command Hander*</u> - is a class which handles business logic for command and mutates data store.

<u>*Process manager*</u> - is a class which coordinates behavior of the domain. Process manager is implemented as a state machine. It can respond event or treat command. It is subscriber on events. So process manager is more general case of Command Handler.

<u>*Command Response*</u> - is a class contained result details of command execution.

<u>*Command Vaidator *</u>- is a class handles validation for the command.

<u>*Bounded Context*</u> - it is a piece of decomposed domain. Other words its autonomous business component defining a clear consistency boundaries.

<u>*Context Map*</u> - abstract representation of iteractions between bounded contexts.

<u>*Command Bus*</u> - indeed it is the pattern. Command bus is an abstract representation wich responsible for iteraction between commands and command handlers. There are exists various sowftware which implements it out of the box or can be used as a command bus: Apache Kafka, Akka Cluster, MS Azure Service Bus etc...

<u>*Event*</u>-  in general event is an entity which reports that something already occured in the past.
But we should take in account two types of events:
* *Event(system)* - event as a communication agent between bounded contexts. That case 		event published after command applied and holds its result.
* *Event(ES)* - event as an enity in event sourcing which representing changes.
Any case event provides an ability to make the full audit trial by saving state of the system.

<u>*Worker*</u> - is a class which responsible for receiving and publishing of commands and events to service bus.

<u>*Snapshots*</u> - is an abstract mark in events range. Instead of replaying all of the persisted events associated with an aggregate when it is rehydrated, can be loaded a recent copy of the state of the aggregate and then replied only the events that were persisted after saving the snapshot.

<u>*Entity*</u> - object defined by identity.  All of fields can be changed over time but not identity.

<u>*Value object*</u> - immutable artifact which identified by its fields (Address as example)

<u>*Service*</u> –stateless artifacs. Service can get parameters and then return result.
