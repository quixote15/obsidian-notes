---
share: true
---

When we are talking about domain driven design we are usually referring to a set of classes with relationships between them.

A aggregate is a subset of classes which interacts amongst themselves and belong to the same sub-domain  and in Object-oriented programming languages thoses aggregates are classes that lives in the same package.


I Could say that aggregates are also:

-  Sub-domain set of classes 
- A collection of domain objects that form a boundary (In DDD this relates to [[Bounded Context]])
- Aggregates are just another way to define boundaries or bounded contexts


Aggregates are the key to designing domain models because they enforce modularization of domains by stablishing boundaries and they also must obey a set of rules that makes the business rules consistent, better implemented and followed for sure.

Rules of aggregates:

1. Reference only aggregate root. For example, a service that uses a repository to load an aggregate must always return the root aggregate to that when updates occur the root aggregate can ensure its invariants
2. Inter-aggregate references must be done by primary keys instead of by tradicional object reference. In microservice architecture this kind of reference is really useful since its easier to maintain and also prevents update mistakes
3. One transaction creates of updates one aggregate


Another important topic related to aggregates are [[Domain Events]]

References:
https://www.youtube.com/watch?v=64ngP-aUYPc