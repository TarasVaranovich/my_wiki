           

Surely event sourcing is one of CQRS implementations and tightly coupled with it.
It stores system state as events, and they are official implementations of domain model.
Speed up is achieved by working with denormalized database schemas.
Event source pattern is more safe and reliable because it based on events' generation only. This case we have any mutable state. Pattern doesn’t imply some events mutations. Events should be generated regularly with appropriate period.

In case of object restoration takes large amount of events we should to do snapshots. \*Snapshot implies store full self-contained state of domain model near to the specific event.
Some optional entity which is not required in events sourcing but necessary to use is \*checkpoint. It implies just a lightweight mark near the specific event and useful in some specific analysis cases.

So events are _commands_ in context of CQRS. In case of failure we implement exception/error as event. We can operate only events in the end.

\* - let consider the explanation of the difference between *snapshots* and *checkpoints* below.
As example we have bank account which holds the sum 100$.
There are a lot of operations applied frequently to our account.

| Event order | Applied operation | Result | Is snapshot | Is checkpoint |
|-------------|-------------------|--------|-------------|---------------|
| 1           | add 5             | 105    | no          | no            |
| 2           | remove 3          | 102    | no          | no            |
| 3           | add 7             | 109    | no          | yes           |
| 4           | remove 13         | 96     | no          | no            |
| 5           | remove 21         | 75     | yes         | no            |
| 6           | add 40            | 115    | no          | no            |
| 7           | add 1             | 116    | no          | yes           |
| 8           | add 4             | 120    | no          | no            |
| 9           | remove 35         | 85     | no          | no            |
| 10          | add 50            | 135    | no          | no            |

Event order represents the Lamport timestamp of applied operation
<u>Be sure real system does not imply storage of the whole 'Result' column. The state of the real entity can be enough large</u>
Snapshots:
In case of billions of rows it will take long time to restore last state of the entity.
We have to apply all operations like *add 5 than remove 3 etc..*
But snapshot helps this case. We are surely know that the state of the entity is consistent near snapshot at timestamp 5. That's why we need to apply to the saved state only operations which are after timestamp 5:
75 + 40 + 1 +4 -35 + 50 = 135
Checkpoints:
Checkpoints can't help in case of consistent object state restoration but useful for analysis. As example, we have checkpoints at timestamps 3 and 7. Then we can find out 
the change of the object in concrete period:
7 - 13 - 21 + 40 + 1 = 14 
Result means *between timestamp 3 and timestamp 7 our account sum was increased by 14$*
