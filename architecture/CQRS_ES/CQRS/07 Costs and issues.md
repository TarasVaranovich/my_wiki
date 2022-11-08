           
 Costs and issues:
- impossible to track count of requests calls
- more complicated multi-threading implementation
- more complicated _reentrancy_ implementation (reentrancy tightly coupled with multi-threading. Means ability to use program by different other programs at the same time, even if first one is in the middle of execution but second only starts)
- sophisticated development in general
- messaging is a weakness
- eventual consistency