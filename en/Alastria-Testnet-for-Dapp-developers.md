# Introduction
The current Alastria Testnet is using [Quorum](https://github.com/jpmorganchase/quorum), an enterprise-focused version of [Ethereum](https://www.ethereum.org/). Quorum is designed for applications requiring high speed and high throughput processing of private transactions within a permissioned group of known participants.

Quorum is a light fork of [go-ethereum](https://github.com/ethereum/go-ethereum) and is updated in line with go-ethereum releases, with the objective of reducing divergence to the absolute minimum. 

The key enhancements over go-ethereum are:
* **Privacy** - Quorum supports private transactions and private contracts through public/private state separation and utilising Constellation, a peer-to-peer encrypted message exchange for directed transfer of private data to network participants.
* **Istanbul BFT** consensus algorithm - with no need for PoW/PoS in a permissioned network, Quorum instead offers multiple consensus mechanisms that are more appropriate for consortium chains. Alastria is currently using Istanbul BFT - a PBFT-inspired consensus algorithm with transaction finality, by AMIS.
* **Peer Permissioning** - node/peer permissioning, ensuring only known parties can join the network.
* **Higher performance** - Quorum offers significantly higher performance than public geth

# Developing applications for Alastria
Because Alastria is using Quorum, developing Smart Contracts for Alastria can be done in much the same way as you would develop Smart Contracts for Ethereum. In general, a Smart Contract developed for Ethereum can be deployed and used in Alastria without modifications, and its functions can be invoked from external programs in exactly the same way via the JSON-RPC API of Geth.

However, if you want to take advantage of the privacy mechanisms that Quorum provides over Ethereum, you have to know:
1. How to deploy a Smart Contract in a way that it is "private", that is, available only to one or more network participants.
2. How to invoke Transactions in a way that they are "private", that is, executed only by one or more network participants.

The modifications required to the application are minimal, but the implications are wide ranging. To know more about Quorum, please visit their Github site: [https://github.com/jpmorganchase/quorum](https://github.com/jpmorganchase/quorum). 

# Deploying Smart Contracts in Alastria
Alastria is a permissioned network, so in general in order to deploy a Smart Contract you have to do it via a node that you (or your organization) have installed and joined to the network. Being permissioned, there are no public nodes with anonymous access like [Infura](https://infura.io/).

The nodes that can be used to deploy Smart Contracts are called "regular nodes" to differentiate them from "validator nodes" which are a special type of nodes executing the IBFT consensus algorithm and that can not be used for anything else in Alastria. You can read a description of validator nodes and their role in the network in this Medium article by one of the implementers: [Istanbul BFT (IBFT)](https://medium.com/getamis/istanbul-bft-ibft-c2758b7fe6ff).

Once you have your regular node connected to the Alastria network, deploying Smart Contracts is basically the same as with Ethereum (with a minor difference if you are deploying a private Smart Contract, as mentioned above).

# How to install a "regular" node
The process to install and connect a node to Alastria is very simple, and consists of the following steps, described in more detail in the Github address [https://github.com/alastria/alastria-node/tree/testnet2](https://github.com/alastria/alastria-node/tree/testnet2):
1. The new node owner installs the software in a machine (physical or virtual) that complies with the minimum requirements.
2. The new node owner requests inclusion of the node into the network by creating a pull request with some of the information created during the installation process, including the unique address of the node (enode).
3. The rest of the network nodes update automatically their permissioning information, and allow the new node to connect.
4. The new node is already part of the Alastria network.

The software for installation and detailed instructions can be found at: [Alastria Telsius node](https://github.com/alastria/alastria-node/tree/testnet2).

# The status of the Testnet
There is already an initial version of the Alastria net composed of around 40 nodes from different entities (at March2019), which is stable enough to enable deployment and testing of Smart Contracts.

Some information about the nodes in Alastria is public, and for the curious readers, you can see the information about the regular nodes that have requested inclusion in the Alastria Testnet here: [Alastria Telsius Regular Nodes](https://github.com/alastria/alastria-node/blob/testnet2/DIRECTORY_REGULAR.md).

The network can be "visualized" in real time via a dedicated instance of the standard [Network Status Monitor](https://github.com/ethereum/wiki/wiki/Network-Status) running at <http://netstats.telsius.alastria.io/>.

# Collaboration tools
* **Mail:** platform@alastria.io
* **How to install an Alastria node:** <https://github.com/alastria/alastria-node/blob/testnet2/docker/README.md>
* **Forum for technical discussions:** Join us at Alastria Slack Channel (see how in <https://github.com/alastria/alastria-node/wiki/HELP>)
* **Alastria consortium web site:** <https://www.alastria.io>
* **EthNetStats for Alastria Testnet:** <http://netstats.telsius.alastria.io/>
* **Block explorer Alastria Testnet:** <https://blkexplorer1.telsius.alastria.io/blocks>

# Some links to useful information
* **Ethereum:** https://www.ethereum.org/
* **Ethereum wiki:** https://github.com/ethereum/wiki/wiki
* **geth wiki:** https://github.com/ethereum/go-ethereum/wiki
* **Solidity:** http://solidity.readthedocs.io/en/develop/
* **Quorum:** https://github.com/jpmorganchase/quorum
* **Nodos plataforma Alastria:** https://github.com/alastria/alastria-node/tree/testnet2
* **Istanbul BFT:** https://github.com/ethereum/EIPs/issues/650
* **Zero Knowledge Proofs:** https://github.com/jpmorganchase/quorum/wiki/ZSL
* **Raft:** https://raft.github.io
