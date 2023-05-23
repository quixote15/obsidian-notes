---
share: true
---

In DDD an event is something that happened to an aggregate.

An event is represented by a class in the domain model which in turn may represents an state change in domain.

Domain events are useful beacause other parties usually are interested in knowing what happened to aggregates.

```
// This is a marker inteface that identifies a class as a domain event
interface DomainEvent {}

// This is a marker interface for all events related to order domain
interface OrderDomainEvent extends DomainEvent {}

// A kind of event in the order domain
class OrderCreated implements OrderDomainEvent {}

// This ensures that we always dispatch events which are inherited from DomainEvent interface
// A generic class parameterized by the domain event type
class DomainEventEnvelope<T extends DomainEvent> {
	// Events metadata 
	private aggregateType: string
	private aggregateId: object

	// the event here...
	private event: T
}

```


In summary events are just plain objects but its useful to created interfaces and classes that identify those events and give them semantic meaning.

#### Event Enrichment

The default behavior of domain events is to container the aggregate id and then  force whoever is consuming thoses events to query or fetch the aggregate in case they need extra information.

The drawback of a consumer querying the service for the aggregate the overhead of service request. An alternative approach is known as event enrichment and consists of sending extra information or all information neeeded in the event.

In that way the consumer no longer will need to query the service for the aggregate information. Here is an example of an enriched event:

```
class OrderCreated implements OrderDomainEvent {
 deliveryInformation: string
 restaurantId: string
 paymentInformation: PaymentInfo
}
```

Because now the order created event contains order details, an event consumer, such as Order History Service no longer needs to fetch that data when processing this event.

Although this simplifies consumers, the **drawback is that it risks making the event classes less stable because thoses classes may need to change whenever consumer's requirements needs to change.**

Trying to satisfy all desires of consumers may be a futile effort but happily identifying which properties to include in an event is fairly obvious and straight foward.

My thoughts on this: Identify most probable properties needed to include in the event and if a consumer needs extra information consider what is better: service request overhead vs modifying event classes.



References: 
https://khalilstemmler.com/articles/typescript-domain-driven-design/chain-business-logic-domain-events/