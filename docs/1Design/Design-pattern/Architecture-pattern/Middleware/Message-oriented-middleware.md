# [Message-oriented middleware](https://en.wikipedia.org/wiki/Message-oriented_middleware)

**Message-oriented middleware** (**MOM**) is software or hardware infrastructure supporting sending and receiving messages between [distributed systems](https://en.wikipedia.org/wiki/Distributed_system). MOM allows [application modules](https://en.wikipedia.org/wiki/Modular_programming) to be distributed over heterogeneous(异质的) platforms and reduces the complexity of developing applications that span（跨越） multiple [operating systems](https://en.wikipedia.org/wiki/Operating_system) and [network protocols](https://en.wikipedia.org/wiki/Network_protocol). The [middleware](https://en.wikipedia.org/wiki/Middleware) creates a **distributed communications layer** that insulates（隔离） the [application developer](https://en.wikipedia.org/wiki/Application_developer) from the details of the various operating systems and network interfaces. [APIs](https://en.wikipedia.org/wiki/API) that extend across diverse platforms and networks are typically provided by MOM.[[1\]](https://en.wikipedia.org/wiki/Message-oriented_middleware#cite_note-1)

This **middleware layer** allows software components (applications, Enterprise JavaBeans, servlets, and other components) that have been developed independently and that run on different networked platforms to interact with one another. Applications distributed on different network nodes use the **application interface** to communicate. In addition, by providing an administrative interface, this new, virtual system of interconnected applications can be made reliable and secure.[[2\]](https://en.wikipedia.org/wiki/Message-oriented_middleware#cite_note-oracle-2)

MOM provides software elements that reside in all communicating components of a client/server architecture and typically support **asynchronous calls** between the client and server applications. MOM reduces the involvement（参与） of application developers with the complexity of the master-slave nature of the client/server mechanism.



## Middleware categories

- [Remote Procedure Call](https://en.wikipedia.org/wiki/Remote_Procedure_Call) or RPC-based middleware
- [Object Request Broker](https://en.wikipedia.org/wiki/Object_Request_Broker) or ORB-based middleware
- Message Oriented Middleware or MOM-based middleware

All these models make it possible for one software component to affect the behavior of another component over a network. They are different in that **RPC- and ORB-based middleware** create systems of **tightly coupled** components, whereas MOM-based systems allow for a [looser coupling](https://en.wikipedia.org/wiki/Loose_coupling) of components. In an **RPC- or ORB-based system**, when one procedure calls another, it must wait for the called procedure to return before it can do anything else. In these [synchronous messaging](https://en.wikipedia.org/w/index.php?title=Synchronous_messaging&action=edit&redlink=1) models, the middleware functions partly as a super-linker, locating the called procedure on a network and using network services to pass function or method parameters to the procedure and then to return results.[[2\]](https://en.wikipedia.org/wiki/Message-oriented_middleware#cite_note-oracle-2)




# 20181203

今天看了Wikipedia上关于[celery](https://en.wikipedia.org/wiki/Celery_(software))的介绍，其中提及celery属于[Message-oriented middleware](https://en.wikipedia.org/wiki/Message-oriented_middleware)。

