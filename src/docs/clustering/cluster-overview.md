---
layout: docs.hbs
title: Akka.Cluster Overview
---
# Akka.Cluster Overview
The best way to begin introducting Akka.Cluster is with brief overview of what it does. Akka.Cluster is the [NuGet package](https://www.nuget.org/packages/Akka.Cluster/1.0.3.11-beta) that brings clustering support to Akka.NET, and it accomplishes this by adding the following capabilities to Akka.NET:

- Makes it easy to create peer-to-peer networks of Akka.NET applications
- Allows peers to automatically discover new nodes and removed dead ones automatically with no configuration changes
- Allows user-defined classes to subscribe to notifications about changes in the availability of nodes in the cluster
- Introduces the concept of "roles" to distinguish different Akka.NET applications within a cluster; and
- Allows you to create clustered routers, which are an extension of the built-in Akka.NET routers, except that clustered routers automatically adjust their routees list based on node availability.

## How is Clustering different from Remoting?
### Internals
Akka.Cluster depends on Akka.Remote under the hood, so anything you could do with Akka.Remote is also supported by Akka.Cluster.

### Use Cases
Akka.Cluster lends itself naturally to high-availability scenarios (generally, AP systems from a [CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem) point-of-view).





## How a Cluster Forms

### Seed Nodes

### Gossip
#### What is Gossip?


### Leader Election
#### What is a Leader?
#### Cluster vs. Role Leader

### Reachability


## Location Transparency
location transparency is THE key to this