These are the tasks that are currently planned in the Alastria Core Platform. The release strategy is ["Time-based Releases"](https://wiki.documentfoundation.org/ReleasePlan), and there is much more detail on the tasks for the immediately upcoming release than for the following ones. The current release is Release 0, which provides an initial Testnet stable enough for developing and testing Ethereum-compatible Dapps and Quorum-compatible Dapps.

# Release 1 (July 2018)
The details and the tracking of the tasks can be seen in the Alastria Core Platform project management tool: [Alastria Platform Core Team Epics](https://tree.taiga.io/project/marcossanlab-alastria-platform/epics).

Below we describe in more detail the contents of the release.

## Network Architecture

### Description of the network Architecture

### Operations of the Network
* Add a new Regular node
* Add a Validator node
* Operations in case of Validator node failure

## Installation and Configuration of the nodes

### Documentation on Github
Improve documentation in <https://github.com/alastria/alastria-node> about all the subjects described below.

### Installation of a Regular node

#### Node installation
Scripts for Ubuntu, CentOS and Red Hat Enterprise Linux 7.4.

Experimental version of a Docker image.

#### Node inclusion into the Testnet
Simple manual procedure based on a Pull Request to the <https://github.com/alastria/alastria-node> repository.

#### Verification that node works with network
Simple verification tests that the node works and that is actually connected to the testnet.

### Installation of a Validator node

#### Node installation
Scripts for Ubuntu, CentOS and Red Hat Enterprise Linux 7.4.

Experimental version of a Docker image.

#### Node inclusion into the Validator set
For node owners: simple manual procedure based on a Pull Request to the <https://github.com/alastria/alastria-node> repository.

For the admins of the current Validator set: centralized automatic process for voting the inclusion of the new node.

#### Verification that node works with network
Simple verification tests that the node works and that is actually connected to the testnet and acting as Validator.

## Network Monitoring

### 1.3.1. Approach to network monitoring
Description of the approach to network monitoring in this release of the testnet. Specially taking into account the following:

* Cyber-security considerations
* Performance considerations
* Requirements on each node

### Monitoring the whole network

* Dashboard
* Detect violations of permissioning policy
* Check network health

### 1.3.3. Validator set

* Check validator set health
* Check throughput
* Detect validator node malfunctioning

### 1.3.4. Node

* Geth
	* Get logs and metrics
	* Get TxPool status
* Machine
	* Get versions of SW components of node
	* Get metrics (CPU, disk, network)
	* Update configuration files from repository

### 1.3.5. Self-update Monitor

## 1.4. Decentralized Network Administration (DNA)

### 1.4.1. Approach to network administration

* Cyber-security considerations
* Performance considerations
* Requirements on each node

### 1.4.2. Whole network

* Coordinate SW upgrade
* Coordinate inclusion of a new Regular node
* Coordinate exclusion of a Regular node

### 1.4.3. Validator set

* Add new node to validator set
* Remove a node from validator set

### 1.4.4. Regular Node

* Restart Geth
* Restart whole node

### 1.4.5. Validator node

* Start/Stop/Update everything

## 1.5. Validator SLA compliance

### 1.5.1. Detection and notification of SLA violations

### 1.5.2. Excluding a failing Validator node

### 1.5.3. Re-inclusion of Validator node

## 1.6. Global incident management

### Reporting from members of Alastria

### Process for responding to incidents

# 2. Release 2

## 2.1. Improve Permissioning mechanism

We require a node permissioning mechanism which can not be modified arbitrarily by participating entities

## 2.2. Improve Un-permissioning mechanism

We require an un-permissioning mechanism that is dynamic and that does not require a restart of all the nodes in the network.

## 2.3. Implement Validator Pool mechanism

Implement a Validator Pool bigger than the current Validator set running the IBFT consensus protocol. Periodically exclude a node from the current Validator set, and include a node taken from the Validator Pool. Initially the algorithm will be round-robbin.

## 2.4 Initial implementation of "bank of gas"

Implement an initial version, to be enhanced with experience, of the "ban of gas", that is the mechanism to assign gas to the accounts of the members so they can execute transactions, while at the same time protecting the network from spam and DoS at the transaction level.

## 2.4. Naming Service
