# 1 General requirements

## 1.1 Based on OpenSource of wide acceptance in the market
1. Alastria will not develop its own blockchain
2. Alastria will not incorporate any proprietary components or force to the members to use any proprietary component.
3. The software used by Alastria should be built by an OpenSource community as wide and as diverse as possible.

## 1.2 The ecosystem of users of the software should be as wide as possible
1. Ecosystem of developers using the software as wide as possible
2. Ecosystem of applications using the software as wide as possible
3. Ecosystem of knowledge about the software as wide as possible

## 1.2 Alastria should be based on general-purpose and multi-industry platforms
Alastria will avoid any software which is specific to one industry or is too specialised.

## 1.3 Alastria will allow and facilitate regulatory compliance by the members, in particular:

1. Reglamento General de Protección de Datos (RGPD)
2. Ley de Servicio de Sociedad de la Información y Comercio Electrónico (LSSI)
3. Reglamento de prevención del blanqueo de capitales y de la financiación del terrorismo
4. Normas y recomendaciones del Consejo Nacional de Ciberseguridad
6. Others

# 2 Technical requirements

## 2.1 Privacy

### 2.1.1 Privacy of Transactional Activity

The members participating in private contracts or transactions should have total privacy of their activity with respect to the other members of Alastria. That is, a member should not be able to see the private activity of any other member if it does not participate itself in that activity. This point does not refer just to data visibility, but also to the actual transactional activity.

### 2.1.2 Privacy of Data

#### 2.1.2.1 No PII data (Personally identifiable information) should be stored in the Blockchain

Alastria can not enforce this just with technical means, so this is more a recommendation to the members. In general, all sensitive data should be stored off-chain, and Alastria will not implement anything that forces sensitive information to be stored in the blockchain.

#### 2.1.2.2 Reference architecture for data storage

Alastria should not force the members to store their data in any specific storage system. Each member should be able to decide which storage system they want to use for each specific type of data items they handle. However, Alastria will provide an architecture and reference implementation that can facilitate to the members and efficient, interoperable and secure storage system.

- Some data could be stored in mobile devices owned by the user.
- Some data could be stored in systems like Constellation from Quorum.
- Some data could be stored in distributed storage systems without access control, like IPFS.
- Some data could be stored in non-distributed storage systems with access control, like WebDAV.
- Some data could be stored in the current systems that act like custodians (eg. banking data, health, ect).

## 2.2 Fault Tolerance

### 2.2.1 Byzantine Fault Tolerance

The system should tolerate attacks from a given number (limited) of nodes and participants behaving maliciously in a deliberate manner.

### 2.2.2 Modular mechanism to upgrade consensus algorithms

Consensus algorithms are evolving very fast. The system should allow to incorporate easily new algorithms, if they are considered adequate for the needs of Alastria.

## 2.3 Performance

1. Throughput around 1.000 tx/s
2. Without performance degradation due to transaction overload.
3. Computational load required for validation of blocks should be independent from time or size of the blockchain.
4. Time required for data access from blockchain should be constant.
5. Should support "pruning" of the blockchain, to facilitate "light clients".


## 2.4 Settlement Finality

1. Transaction finality should be deterministic and considered final in one block.

## 2.5 Without embedded cryptocurrencies

In order to achieve zero or very low and predictable transaction costs (non-zero transaction costs could be required for anti-spam and network-protection mechanisms).

## 2.6 Anti-spam

1. Anti-spam mechanism to protect the network from nodes and participants that generate excessive load.
2. Mechanism to stop immediately entities which initiate transactions above a certain level

## 2.7 Permissioning

1. Permissioning of individual nodes and of participant addresses
2. Whitelist and blacklist of nodes and participant addresses


## 2.8 Maximise decentralisation

The objective of Alastria is to be as much as possible a public network, in contrast to a private consortium. When adopting any decision, the option chosen should be the one which maximises decentralisation, assuming that the rest of requirements are achieved.

## 2.9 Inter-node connectivity

1. Minimise the need for direct point-to-point connectivity between participant nodes.
2. Minimise the need for direct point-to-point connectivity between participant nodes in private transactions and contracts.

## 2.10 Synchronisation and Disaster Recovery

1. Mechanism for fast synchronisation of the blockchain for nodes which connect for the first time, both for the public and the private parts.
2. Mechanism that allows starting a new node from the backup of another node, till a given block.
