
# Server Affinity Technical Approach

Server Affinity is a concept within load balancing and clustering. It refers to load balancing a user's request and routing the request from the user's session to the appropriate application server. Many legacy applications were designed with session state persisting within the application server itself. As this persisting session state exists, it causes an issue to migrate the application into the Azure. Refactoring the application to store their state within a load balancer or cluster configuration utilizing Server/Session Affinity is a technique one could use to address the issue. But how do we refactor an application that uses persisting session states within applications?

In detail, session affinity directs all requests in a session to a specific application server by routing the session from client to the application server. The use of session affinity enhances the application performance by using in-memory caching instead of a database. There are several different Session Affinity concepts load balancers use.

1. Hash-based Distribution Mode - The default method for Azure load balancer. More specifically, Azure Load Balancer uses the five-tuple hash. A tuple is composed of the following:
   1. Source IP
   2. Source port
   3. Destination IP
   4. Destination port
   5. Protocol type
2. Cookie based Session Affinity - Where sessions are determined by Cookies


## Hash-based Distribution Mode