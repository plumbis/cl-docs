---
title: Data Center Network Deployments
author: NVIDIA
weight: 70
toc: 4
---

This section describes three common data center deployment types for network management:

- Out-of-band management (recommended)
- In-band management
- Server cluster and high availability

{{<notice note>}}

NetQ operates over layer 3, and can operate in both layer-2 bridged and layer-3 routed environments. NVIDIA recommends a layer-3 routed environment whenever possible.

{{</notice>}}

<!-- vale off -->
## Out-of-band Management Deployment
<!-- vale on -->

NVIDIA recommends deploying NetQ on an out-of-band (OOB) management network to separate network management traffic from standard network data traffic. 

The physical *network* hardware includes:

- **Spine** switches: aggregate and distribute data; also known as an aggregation switch, end-of-row (EOR) switch or distribution switch
- **Leaf** switches: where servers connect to the network; also known as a top-of-rack (TOR) or access switch
- **Server** hosts: host applications and data served to the user through the network
- **Exit** switch: where connections to outside the data center occur, also known as a border leaf or service leaf
- **Edge** server (optional): where the firewall is the demarcation point, peering can occur through the exit switch layer to Internet (PE) devices
- **Internet** device: where provider edge (PE) equipment communicates at layer 3 with the network fabric

The following figure shows an example of a Clos network fabric design for a data center using an OOB management network overlaid on top, where NetQ resides. The physical connections are displayed as gray lines, connecting Spine01 to four leaf and two exit devices; Spine02 is connected to the same leaf and exit devices. Leaf01 and Leaf02 connect to each other over a peerlink and act as an MLAG pair for Server01 and Server02, as do Leaf03 and Leaf04 for Server03 and Server04. The edge connects to both exit devices, and the Internet node connects to Exit01.

{{<img src="/images/netq/deploy-arch-dc-example-230.png" alt="diagram of a Clos network displaying connections between spine switches, leafs, servers, and exit switches." ewidth="700">}}

The physical *management* hardware includes:

- OOB management switch: aggregation switch that connects to all network devices through communications with the NetQ Agent on each node
- NetQ Platform: hosts the telemetry software, database, and user interfaces

These switches connect to each physical network device through a virtual network overlay, as shown below.

{{<img src="/images/netq/deploy-arch-oob-example-230.png" alt="diagram displaying connections between physical network hardwar and physical management hardware with a virtual network overlay" ewidth="700">}}

<!-- vale off -->
## In-band Management Deployment
<!-- vale on -->

While not recommended, you can implement NetQ within your data network. In this scenario, there is no overlay and all traffic to and from the NetQ Agents and the NetQ Platform traverses the data paths along with your regular network traffic. The roles of the switches in the Clos network are the same, except that the NetQ Platform performs the aggregation function that the OOB management switch performed. If your network goes down, you might not have access to the NetQ Platform for troubleshooting. Certain features—such as lifecycle management—require {{<link url="Lifecycle-Management/#lcm-support-for-in-band-management" text="additional configurations">}} for in-band deployments.  

{{<img src="/images/netq/deploy-arch-ib-example-230.png" alt="diagram of an in-band management deployment." ewidth="700">}}
## Server Cluster Deployments

NetQ supports a server cluster deployment for users who prefer a solution with increased scalability in which the collected data by the NetQ Platform remains available through additional servers if one should fail for any reason. In this configuration, three NetQ Platforms are deployed, with one as the master and two as workers (or replicas). NetQ Agents send data to all three servers so that if the master NetQ Platform fails, one of the replicas automatically becomes the master and continues to store the telemetry data. The following example is based on an OOB-management configuration, and modified to support higher scalability for NetQ.

{{<img src="/images/netq/deploy-arch-ha-example-240.png" alt="diagram of a server cluster deployment with one master and two worker NetQ platforms." ewidth="700">}}

### High Availability

You can configure a server cluster with a high-availability, virtual IP address for load balancing control plane processing and UI access across all nodes of a cluster deployment. This deployment model requires an additional IP address that is allocated in the same subnet as the master and worker nodes. The virtual IP address also enables UI access in the case of a master node failure. The virtual IP address must be specified during a new {{<link title="Install the NetQ System" text="high-availability server cluster installation">}} with the `cluster-vip` option specified in the {{<link url="install/#netq-install-cluster-full" text="install command">}}.

High availability is only supported for on-premises deployments.


