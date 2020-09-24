
# Server Affinity Technical Approach

## Persisting Session

Many legacy applications were designed with session state persisting within the application server itself. As this persisting session state exists, it causes an issue to migrate the application into Azure. When refactoring is not a possibility, Azure App Service with Application Request Routing (ARR) Affinity i.e Sticky Session can be used.

## Session Affinity

Session Affinity or Sticky sessions is a concept within load balancing and clustering. It refers to load balancing a user's request and routing the request from the user's session to the appropriate application server. The use of session affinity enhances the application performance by using in-memory caching instead of a database fore stateful applications. Several concepts of session affinity are:

- Source Ip affinity distribution mode
  
- Session Cookie

- Application Request Routing (ARR) Affinity i.e Sticky session

When refactoring an app is not possible, Azure App Service has a feature called ARR Affinity. It is when a user will always be routed to the same host machine during the client's session.

## ARR Affinity in Azure App Service

Azure App Service defines a set of compute resources for web apps to run. One of the features App Services has is Traffic Manager integration and more specifically AAR Affinity sessions.

AAR Affinity is used for stateful applications that can not be refactored to become stateless. When ARR Affinity is enabled, it turns the IIS server into a load balancer and attaches a cookie onto sessions so that client will always communicate with the same instance within their session. While this increases the compatibility for stateful applications and applications not designed with load balancing in mind, ARR Affinity is not recommended for state-less applications and can cause performance issues due to the constraint of how the traffic is distributed to the application server. Refactoring an application to become stateless increases performance and the load balancer is free to distribute the session traffic for the best optimized routes.

## Implementing ARR Affinity on a Stateful Application


## Stateful vs Stateless Applications


## Refactoring Stateful Applications

