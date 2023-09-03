---
share: true
---

Those are the most simple form of datastore and most programming languages provide in memory key-value stores such as Map container in c++, Hashmap in java or dictionary in python. 

They usually have this interfaces:
- Get(key)
- Set(key, value)
- delete(key)


Under the hook most implementations use hash tables or some variation of a self balancing tree (B-trees or Red-black- trees).

Key-Value stores are part of the [[noSQL movement]]. NoSQL databases  presents the user with a interface which is not SQL and some say that is "no only SQL".

###  Key-value stores and relational databases
In Key-value stores you cannot query by values like in relational database and do not have schemas. If you dont know the key you are trying to find you'd have to iterate through the dataset.

Even though key-value stores outperforms relational databases this implies that you should have previous knowledge of the key.

Although some key-value stores can store structure data and have fields omdexed.


Reading required:

Before going to part two one should read those:

This article gives a review of the [NOSQL Ecosystem](https://aosabook.org/en/v1/nosql.html)  and this article gives a [Key Value Stores: A Practical Overview](http://blog.marc-seeger.de/2009/09/21/key-value-stores-a-practical-overview/).

