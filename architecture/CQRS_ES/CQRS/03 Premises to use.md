The incentives to apply CQRS is particular context:
- complex/difficult domain models. As example models contain complex update operations which concern difficult contexts. It much eaiser to consider mentioned before models as an events than as a set of complex connections between them.
- high-load systems. In case of high-load system you could leverage CQRS since it allows to scale separate parts of system in a very flexible way. You could also separate mutation and reading.
- \*collaborative domains where actors access the same data in parallel
- task-based business-logic. As example bank transactions which provides delta of state calculation. Current case any task can be implemented as a sequence of events invocations.
- when number of reads is greater than number of writes. Most suitable case for reading and writing loads separation.

\* - let consider the example below.
We have some restricted places count. For instance tickets on the flight.
Some people book tickets and some cancel booking.  Additionally bookkeeping can change tickets prices, navigation center can change flight information for a reason of whether etc.
Flight  information is used for multiple actors like an accountment center(which calculates seating arrangment for the right gravity center), meal supplier, bookkeeping, customs house etc.
For more information we should take in account that all of data consumers do not need consistent data immidiately. Means we won't have some strict ACID transactions like in the bank system. The data will be consumed let us say once a day until flight occurs. Eventual consistency is sufficient this case.
Multiple data suppliers and consumers are represent *colloborative domain*.


![[CQRS_03.png]]

So we have three actors who changes data and four who reads. Just imagine if four readers will blocked by transactions of three writers.