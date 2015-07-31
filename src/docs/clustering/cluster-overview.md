---
layout: docs.hbs
title: Akka.Cluster Overview
---

# Akka.Cluster Overview
## What is a "Cluster"?
A cluster represents a fault-tolerant, elastic, decentralized peer-to-peer network of Akka.NET applications with no single point of failure or bottleneck. Akka.Cluster is the module that gives you the ability to create these applications.

## What Does Akka.Cluster Do?
The best way to begin introducing Akka.Cluster is with brief overview of what it does. Akka.Cluster is the [package](https://www.nuget.org/packages/Akka.Cluster/1.0.3.11-beta) that brings clustering support to Akka.NET, and it accomplishes this by adding the following capabilities to Akka.NET:

- Makes it easy to create peer-to-peer networks of Akka.NET applications
- Allows peers to automatically discover new nodes and removed dead ones automatically with no configuration changes
- Allows user-defined classes to subscribe to notifications about changes in the availability of nodes in the cluster
- Introduces the concept of "roles" to distinguish different Akka.NET applications within a cluster; and
- Allows you to create clustered routers, which are an extension of the built-in Akka.NET routers, except that clustered routers automatically adjust their routees list based on node availability.

## How is Clustering Different From Remoting?
Akka.Cluster is a layer of abstraction on top of Akka.Remote, that puts Remoting to use for a specific structure: clusters of applications. Under the hood, Akka.Remote powers Akka.Cluster, so anything you could do with Akka.Remote is also supported by Akka.Cluster.

Generally, Akka.Remote serves as plumbing for Akka.Cluster and other "high availability" modules within Akka.NET. You would generally only use Akka.Remote by itself in scenarios that don't require the elasticity and fault-tolerance needs that Akka.Cluster provides.

Essentially, Akka.Cluster extends Akka.Remote to provide the basis of scalable

### Use Cases
Akka.Cluster lends itself naturally to high-availability scenarios (generally, AP systems from a [CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem) point-of-view).

### Cluster Gossip
To understand how clusters form and run, you need to first understand what powers them: gossip.

#### What is Gossip?
"[Gossip](https://en.wikipedia.org/wiki/Gossip_protocol)" is the ongoing flow of messages that are passed between nodes in a cluster, updating cluster members of the state of each member of the cluster.

Gossip events are sent continually around the cluster on many events, such as when a node joins the cluster, leaves the cluster, becomes unreachable by other nodes, etc.

Gossip events fall into three categories:

1. Member events: gossip messages sent when a node joins, starts leaving, and exits the cluster.
2. Reachability events: gossip messages sent when a node loses (or regains) contact with another member of the cluster.
3. Metrics events (not implemented yet): gossip messages detailing node resource consumption such as CPU and memory utilization.

## How a Cluster Forms
### Nodes
First of all, let's define some terminology. What is a node? A node is a logical member of a cluster. A node is defined by the address at which it is reachable (hostname:port tuple). Because of this, more than one node can exist simultaneously on a given machine.

### Seed Nodes
Seed nodes are the service-discovery mechanism of Akka.Cluster: a seed node is a well-known contact point that new nodes contact in order to join the cluster.

This is what the process of a node joining the cluster looks like:




> [Lighthouse](https://github.com/petabridge/lighthouse) is a dedicated seed node tool that you can use.




### Leader Election
#### What is a Leader?
#### Cluster vs. Role Leader

### Reachability


## Location Transparency
location transparency is THE key to this


### References & Further Info
- [How to Create Scalable Clustered Akka.NET Apps Using Akka.Cluster](https://petabridge.com/blog/intro-to-akka-cluster/)
- [Video: Introduction to Akka.Cluster](https://www.youtube.com/watch?v=mUTKvGyxbOA)
- [Gossip Protocol](https://en.wikipedia.org/wiki/Gossip_protocol)