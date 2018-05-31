# Alastria Core Technical Platform
## Requirements and challenges for a country blockchain network

<!-- TOC -->

- [Alastria Core Technical Platform](#alastria-core-technical-platform)
    - [Requirements and challenges for a country blockchain network](#requirements-and-challenges-for-a-country-blockchain-network)
- [1. Objective](#1-objective)
- [2. Introduction](#2-introduction)
- [3. General characteristics of the main blockchain technologies](#3-general-characteristics-of-the-main-blockchain-technologies)
- [3. The Public-Permissionless blockchain networks](#3-the-public-permissionless-blockchain-networks)
    - [3.1. The problem of Scalability of Public-Permissioned blockchains](#31-the-problem-of-scalability-of-public-permissioned-blockchains)
    - [3.2. The problem of Transaction Costs: High and Volatile](#32-the-problem-of-transaction-costs--high-and-volatile)
    - [3.3. The problem of Privacy](#33-the-problem-of-privacy)
        - [3.3.1. Confidentiality of Data](#331-confidentiality-of-data)
        - [3.3.2. Privacy of Transactional Activity](#332-privacy-of-transactional-activity)
- [4. THE PRIVATE CONSORTIUM BLOCKCHAIN NETWORKS](#4-the-private-consortium-blockchain-networks)
    - [4.1. A different “Trust trade-off”](#41-a-different-trust-trade-off)
    - [4.2. A different incentivisation model for operating nodes](#42-a-different-incentivisation-model-for-operating-nodes)
    - [4.3 A different Transaction execution model](#43-a-different-transaction-execution-model)
- [5. ALASTRIA: A PUBLIC-PERMISSIONED BLOCKCHAIN NETWORK](#5-alastria--a-public-permissioned-blockchain-network)
- [6. GENERAL REQUIREMENTS ABOUT THE SOFTWARE](#6-general-requirements-about-the-software)
    - [6.1. Based on OpenSource of wide acceptance in the market](#61-based-on-opensource-of-wide-acceptance-in-the-market)
    - [6.2. The ecosystem of users of the software should be as wide as possible](#62-the-ecosystem-of-users-of-the-software-should-be-as-wide-as-possible)
    - [6.3. Alastria should be based on general-purpose and multi-industry platforms](#63-alastria-should-be-based-on-general-purpose-and-multi-industry-platforms)
    - [6.4. Alastria will allow and facilitate regulatory compliance by the members, in particular:](#64-alastria-will-allow-and-facilitate-regulatory-compliance-by-the-members--in-particular)
- [7. REFERENCE ARCHITECTURE OF A BLOCKCHAIN](#7-reference-architecture-of-a-blockchain)
    - [7.1. Infrastructure layer](#71-infrastructure-layer)
        - [7.1.1. Data Storage](#711-data-storage)
        - [7.1.2. Runtime Environment (Compute)](#712-runtime-environment-compute)
        - [7.1.3. Communication Networks](#713-communication-networks)
    - [7.2. DLT Platform layer](#72-dlt-platform-layer)
        - [7.2.1. Secure Runtime](#721-secure-runtime)
        - [7.2.2. Smart Contract](#722-smart-contract)
        - [7.2.3. Ledger](#723-ledger)
        - [7.2.4. State Management](#724-state-management)
        - [7.2.5. Transaction System](#725-transaction-system)
        - [7.2.6. Membership Services](#726-membership-services)
        - [7.2.7. Consensus Mechanism](#727-consensus-mechanism)
            - [7.2.7.1. Trust and Validator nodes in IBFT](#7271-trust-and-validator-nodes-in-ibft)
            - [7.2.7.2. Selection of Validator nodes](#7272-selection-of-validator-nodes)
            - [7.2.7.3. Number of Validator nodes](#7273-number-of-validator-nodes)
        - [7.2.8. Event Distribution](#728-event-distribution)
        - [7.2.9. Crypto Services](#729-crypto-services)
        - [7.2.10. Secure Inter-Node Communication](#7210-secure-inter-node-communication)
    - [7.3. API layer](#73-api-layer)
        - [7.3.1. External Interfaces](#731-external-interfaces)
        - [7.3.2. User API](#732-user-api)
        - [7.3.3. Admin API](#733-admin-api)
    - [7.4. User layer](#74-user-layer)
        - [7.4.1. User Applications](#741-user-applications)
        - [7.4.2. Administration Applications](#742-administration-applications)
    - [7.5. Non-DLT Systems Layer](#75-non-dlt-systems-layer)
        - [7.5.1. DLT Oracles](#751-dlt-oracles)
        - [7.5.2. Non DLT Applications](#752-non-dlt-applications)
        - [7.5.3. Off Ledger Data](#753-off-ledger-data)
    - [7.6. Cross-layer functions](#76-cross-layer-functions)
        - [7.6.1. Development](#761-development)
            - [7.6.1.1. IDE (Integrated Development Environment)](#7611-ide-integrated-development-environment)
            - [7.6.1.2. Build Management](#7612-build-management)
            - [7.6.1.3. Test Management](#7613-test-management)
        - [7.6.2. Management and Operations](#762-management-and-operations)
            - [7.6.2.1. Service directory](#7621-service-directory)
            - [7.6.2.2. Incident Management](#7622-incident-management)
            - [7.6.2.3. Delivery Management](#7623-delivery-management)
            - [7.6.2.4. Node Management](#7624-node-management)
            - [7.6.2.5. Ledger Management](#7625-ledger-management)
            - [7.6.2.6. DLT System Management](#7626-dlt-system-management)
            - [7.6.2.7. Monitoring](#7627-monitoring)
            - [7.6.2.8. Update and Version Management](#7628-update-and-version-management)
        - [7.6.3. Security capabilities](#763-security-capabilities)
            - [7.6.3.1. Authentication and Identity Management](#7631-authentication-and-identity-management)
            - [7.6.3.2. Security Policy Management](#7632-security-policy-management)
            - [7.6.3.3. Access Management](#7633-access-management)
            - [7.6.3.4. PII Protection](#7634-pii-protection)
        - [7.6.4. Governance and Compliance](#764-governance-and-compliance)
            - [7.6.4.1. Supervisory Support](#7641-supervisory-support)
            - [7.6.4.2. Audit Support](#7642-audit-support)
            - [7.6.4.3. Governance Controls](#7643-governance-controls)
            - [7.6.4.4. Policy Management](#7644-policy-management)

<!-- /TOC -->

# 1. Objective
This document describes the requirements and challenges for a country blockchain network like Alastria. While the document tries to be as technology-agnostic as possible, there are subjects where we have to focus on a given technology, and when this is the case, we discuss the initial implementation using Quorum. However, the intention is to include specific analyses for other technologies like Hyperledger.  This document is live and continuously evolving, describing the current situation of the technology with respect to the requirements and the challenges that have to be solved.

# 2. Introduction

Alastria is a Spanish nonprofit association with the objective to create the first multi-industry national blockchain network, to support transactions with full legal validity, and with appropriate levels of privacy.

We are currently more than 250 companies and institutions from different sectors like banking, telco, energy, insurance, law firms, technology and services companies, research institutions, universities, etc.. The association is growing, because it is inclusive and open to anybody who would like to collaborate and participate in the initiative.

The associates of Alastria are collaborating with each other in the definition, deployment, operation and maintenance of the infrastructure, but will compete with each other in the specific use cases built on top of the network.

Being a country-wide blockchain network, Alastria is neither a public-permissionless network nor a private consortium. Alastria shares some of the properties of both types of networks, but it has some requirements of its own. This document is structured as follows:
* The first two sections describe the general characteristics of Public-Permissionless and Consortium blockchains and the problems that they present for a network like Alastria
* Then we describe the specific requirements of Alastria, using as a scheme and guiding theme a general Reference Architecture of blockchains systems

# 3. General characteristics of the main blockchain technologies

Distributed fault tolerant protocols have been deployed traditionally at relatively small scale, and typically in a single administrative domain (that is, inside a single legal company) where adversarial attacks can be minimized and so they are not a primary concern.

[Bitcoin](https://bitcoin.org/bitcoin.pdf) was the first practical system to solve the problem of fault tolerant distributed computing in a completely public and anonymous environment where anonymous malicious adversaries could behave in a [Byzantine](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance) way to try to make the network malfunction.

Possibly the major invention of the Bitcoin system was to design a consensus mechanism with an embedded digital currency, where agreement on the order of transactions is negotiated via an economically incentivized cryptographic random lottery based on partial hash collisions. This novel consensus algorithm was called Proof-of-Work (PoW), reflecting the idea that in order to win the lottery, the nodes had to use a lot of computational resources to solve the cryptographic puzzle used for the lottery.

Apart from enabling the consensus on the order of transactions, the PoW mechanism provides two additional benefits: on one hand it protects the system from Sybil attacks (especially difficult to avoid in public-permissionless networks), and on the other it creates a very good incentivisation mechanism for promoting anonymous participants to dedicate expensive computing resources to execute the consensus algorithm required for the operation of the network and ensuring safety.

The [Bitcoin](https://bitcoin.org/bitcoin.pdf) and [Ethereum](https://www.ethereum.org/) systems are very robust and they operate successfully in a highly adversarial environment, where highly-motivated and malicious attacks are commonplace, and does so in spite of the anonymity of the entities operating the nodes in a fully decentralized way. This is the reason why the system is many times referred to as the “Trustless machine”.

> A brief note on terminology: we refer to these types of networks as "Public-Permissionless" to stress the fact that the participants do not need to request permission to anybody in order to participate in the network. It is very common in the literature to drop the "Permissionless" word and just use "Public" to mean both accessible to anybody and without the need to request permission.
>
> However, in other contexts, the word "Public" does not necessarily imply the anonymous access to the services provided in a public manner. For example, in order to access to the public health services of a country, their citizens normally have to identify themselves to the entity providing the service. In those other contexts there are many examples of both Public-anonymous and Public-identified provision of public services.
>
> Indeed, we will see that Alastria has the objective of being a Public-Permissioned network, in the sense that is is open to all entities in Spain, but it is permissioned so the entities have to be identified.

Soon, the underlying technology powering these systems started to find applicability in other environments where the requirements for decentralization were not so high, even though it was required a high level of collaboration among peers (typically enterprises), higher than what was possible with the current centralized technologies. A set of distributed systems started to appear with some characteristics that were not possible before, with numerous fields of application and with enormous potential for innovation.

A class of these systems is what is known as Private Consortiums Blockchains, because they have the objective to improve efficiency in the creation of consortiums or groups of companies and entities, without the existence of centra entities which operate a centralized database or transactional system, acting as the central point to which all other entities have to connect. In this sense, we can say that private consortium blockchains allow the implementation of the P2P paradigm among companies, instead of among individuals, as it was the original objective of Bitcoin.

Two of the most widely used technologies for private consortiums are Quorum and Hyperledger Fabric (or simply Fabric).
In order to understand the pros and cons of the different technologies, it is first convenien to analyze some of the characteristics of blockchain systems, public and private, and how Ethereum, Quorum and Fabric approach each of those characteristics.

In the following sections, we analyze the different tecnologies according to these characteristics:

* Transaction execution model
* Scalability
* Immutability
* Privacy
* Safety

# 3. The Public-Permissionless blockchain networks

Distributed fault tolerant protocols have been deployed traditionally at relatively small scale, and typically in a single administrative domain (that is, inside a single legal company) where adversarial attacks can be minimized and so they are not a primary concern.

[Bitcoin](https://bitcoin.org/bitcoin.pdf) was the first practical system to solve the problem of fault tolerant distributed computing in a completely public and anonymous environment where anonymous malicious adversaries could behave in a [Byzantine](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance) way to try to make the network malfunction.

Possibly the major invention of the Bitcoin system was to design a consensus mechanism with an embedded digital currency, where agreement on the order of transactions is negotiated via an economically incentivized cryptographic random lottery based on partial hash collisions. This novel consensus algorithm was called Proof-of-Work (PoW), reflecting the idea that in order to win the lottery, the nodes had to use a lot of computational resources to solve the cryptographic puzzle used for the lottery.

Apart from enabling the consensus on the order of transactions, the PoW mechanism provides two additional benefits: on one hand it protects the system from Sybil attacks (especially difficult to avoid in public-permissionless networks), and on the other it creates a very good incentivisation mechanism for promoting anonymous participants to dedicate expensive computing resources to execute the consensus algorithm required for the operation of the network and ensuring safety.

The [Bitcoin](https://bitcoin.org/bitcoin.pdf) and [Ethereum](https://www.ethereum.org/) systems are very robust and they operate successfully in a highly adversarial environment, where highly-motivated and malicious attacks are commonplace, and does so in spite of the anonymity of the entities operating the nodes in a fully decentralized way. This is the reason why the system is many times referred to as the “Trustless machine”.

A brief note on terminology: we refer to these types of networks as "Public-Permissionless" to stress the fact that the participants do not need to request permission to anybody in order to participate in the network. It is very common in the literature to drop the "Permissionless" word and just use "Public" to mean both accessible to anybody and without the need to request permission.

However, in other contexts, the word "Public" does not necessarily imply the anonymous access to the services provided in a public manner. For example, in order to access to the public health services of a country, their citizens normally have to identify themselves to the entity providing the service. In those other contexts there are many examples of both Public-anonymous and Public-identified provision of public services.

Indeed, we will see that Alastria has the objective of being a Public-Permissioned network, in the sense that is is open to all entities in Spain, but it is permissioned so the entities have to be identified.

## 3.1. The problem of Scalability of Public-Permissioned blockchains
However, achieving this level of robustness in such a hostile environment can not be made without some compromises. Those compromises are better illustrated using the words of Vitalik Buterin describing the **“Blockchain trilemma”**. The trilemma claims that blockchain systems can only at most have two of the following three properties:
* **Decentralization**, defined as the system being able to run in a scenario where each participant only has access to O(c) resources, where c refers to the size of computational resources available to each node (ie. a regular laptop or small VPS).
* **Scalability**, defined as being able to process O(n) > O(c) transactions, where n refers to the size of the ecosystem in some abstract sense.
* **Security (or Safety)**, defined as being secure against attackers with up to O(n) resources

For the reasons described above, Public-Permissionless blockchains have chosen Decentralization and Security over Scalability.

In general, we assume that in practice all useful implementations of blockchain systems will always want to stress Safety, so we are in reality faced with a dilemma between Decentralization and Scalability, which we call the “Trust continuum” as shown in Figure 1.

But it happens that these properties are not binary all-or-nothing, especially if we add permissioning into the picture, as it will be discussed below.

As Figure 1 describes, the prevailing public-permissionless blockchain networks currently in production like Bitcoin or Ethereum have the very desirable property of being “Trustless”, but due mainly to the characteristics of the consensus algorithms used to achieve that property, they suffer from very well documented scalability problems. There are a lot of efforts being made to solve or alleviate the scalability problem, but as of today, the problem still exists and permissioned networks will always have several orders of magnitude better performance.

***

![Trust Continuum](/assets/Trust%20continuum_%20trustless%20vs%20centralized.jpg)
<p align="center"><b>Fig1. - The Trust Continuum.</b></p>

***

## 3.2. The problem of Transaction Costs: High and Volatile
As we mentioned before, we expect that all practical implementations of blockchains would not compromise on Security.

In such a highly adversarial environment as a public anonymous fully decentralized network, there should be crypto-economic incentives for the miner nodes to perform their duties and ensure the security of the network. As Vitalik Buterin says in ["On Inflation, Transaction Fees and Cryptocurrency Monetary Policy"](https://blog.ethereum.org/2016/07/27/inflation-transaction-fees-cryptocurrency-monetary-policy/):
> The primary expense that must be paid by a blockchain is that of security. The blockchain must pay miners or validators to economically participate in its consensus protocol, whether proof of work or proof of stake, and this inevitably incurs some cost. There are two ways to pay for this cost: inflation and transaction fees. Currently, Bitcoin and Ethereum, the two leading proof-of-work blockchains, both use high levels of inflation to pay for security.

As described in Figure 1, those crypto-economic incentives for the miner nodes cause that the transaction costs for users of the network are very high and very volatile. While this is not a problem for some uses cases (specially ones requiring very low transaction volumes), high and unpredictable transaction costs constitute a critical limitation for a network like Alastria where we expect the provision of basic services and a very high number of transactions, many of them with low added-value for the originator but still required for the implementation of the commercial transactions.

Expected improvements to the current public-permissionless blockchain systems may alleviate somewhat this problem, but they will not solve the fundamental problem of securing the network in conditions of anonymity.

## 3.3. The problem of Privacy
By default, in public blockchains like Bitcoin or Ethereum, transactions are executed by all nodes in the network, transactions are globally published and state data is not encrypted in most applications, so all participants have access to all data stored in the ledger without any restriction.

In many cases, the only privacy mechanism is the pseudonymity nature of account addresses involved in the transactions, which is a poor method to provide real privacy.

There are many efforts to incorporate natively in the blockchain privacy-preserving technologies, with the promise that they will allow users to benefit from the security of a blockchain, using a decentralized network to process the transactions, but “encrypting” the data in such a way that even though everything is being computed in plain sight, the underlying “meaning” of the information is completely obfuscated.

This is what Vitalik Buterin calls the “holy grail” of blockchain privacy technology, and the technologies  are promising but currently they are either too cumbersome or too slow (or both) for widespread and immediate adoption by the majority of developers.

Discussing in detail the “holy grail” of privacy-enhancing technologies is out of scope for this document (but is the subject of a separate specific one in the future). In most cases, developers are currently forced to design partial, off-chain and ad-hoc solutions, many times specific to the use cases they are addressing. 

Privacy is a complex subject, but for the purposes of this document, we will describe two different aspects of privacy related to blockchain applications: Confidentiality of Data and Privacy of Transactional Activity.

### 3.3.1. Confidentiality of Data
This refers to the ability to keep data private, so unauthorized parties can not see it. This is especially relevant with personal data in the case of natural persons, where “personal data” has the meaning described in the GDPR.

Simple solutions like storing only encrypted data in the blockchain are very delicate, as they can create other problems: if the key to decrypt specific information is lost, the data may not be recovered in the future. Furthermore, if a key is stolen and published, all the data is forever decrypted in the blockchain since the data cannot be altered.

Storing data off-chain and using hashes on-chain can alleviate the second problem, but it comes with its own set of challenges. For example, in Ethereum, all data that is needed to execute a Smart Contract has to be on-chain at the moment of execution (either coming from the global state of the contract or via the payload of the transaction that triggered the execution). The Smart Contract executes inside the EVM and so it does not have access to the data which is stored off-chain at the moment of execution. Given that transaction payloads are stored in the blockchain, they are available to all participants. The same happens with the global state.

As will be seen later, blockchains designed for private consortiums try to solve this problem by storing private data only in the nodes which are party on the transaction, like Quorum, Hyperledger or Corda. However, in most cases this has to be complemented by the off-chain techniques mentioned above. More detailed information of the techniques that can be used is given in the appropriate section further in this document.

### 3.3.2. Privacy of Transactional Activity
Even though transaction payload and state data could be encrypted, the transactional activity in the blockchain produces metadata. In a public blockchain where the metadata is accessible to all parties, statistical analysis applied to this metadata could make pattern recognition and correlation possible, revealing some information, especially if complemented with external data.

One clear example of this is the “From” and “To” fields in the transaction header in the public Ethereum network. The “From” field is the same for all transactions initiated by a given account, and it is accessible to all participants in the network. Initially, nobody knows the association of a given account with a physical entity in the real world. But if someone, using external information, can derive the association for just one transaction, then they can know the whole transaction history of the associated entity. The same applies to the “To” field, even if it refers to a Smart Contract address.

In a context where members interacting to each other are executing legal transactions (like one company buying mechanical components to its suppliers), the on-chain addresses of each party should be associated to a real entity, and so well known by each party. That means that in a public network like Ethereum, once an entity has transacted with another one, each of the entities know each other’s full transaction history, both in the past and in the future. Even if the actual transaction data is encrypted, there is a lot of information that could be derived (by competitors, for example) from knowing the transactional activities and flows among the parties.

This is not acceptable in a real commercial setting, where the members should have total privacy of their activity with respect to the other members of the network. That is, a member should not be able to see the private activity of any other member if it does not participate itself in that activity. Again, this point does not refer just to data visibility, but also to the actual transactional activity.

Having said that, there may be some legal persons which (eg. for transparency reasons), voluntarily take the decision to make all metadata public (or even the whole data, if it is compatible with the law).

An even stricter scenario is when one of the parties in the transaction is a natural person, due to the required compliance to GDPR.  Even if the personal data is encrypted, leaking transactional metadata which makes statistical analysis possible is not just a commercial decision, but it carries legal and compliance implications.

Another example of leaking metadata is the following: a naive approach to data privacy is encrypting data and using just the hash in the transactions or storing it in the state. If the same hash is reused in many transactions, even if data is encrypted and stored off-chain (like in IPFS), correlation could be performed with the undesirable results just described above. If the source of the encrypted data is personal data, then the system is just pseudonymous and, according to GDPR, the hash in the blockchain should be treated as personal data. And storing personal data in the blockchain where it is accessible to everybody is a very bad idea if not just plain illegal.
As mentioned above, while waiting for  the “holy grail” of privacy-preserving technologies to be implemented natively in public blockchains and made practical to use by the general public, care should be taken to ensure privacy by using other not-so-fancy, but very well know mechanisms coming from the “traditional” world. Some possibilities (and challenges) will be described in a dedicated section below in this document.

# 4. THE PRIVATE CONSORTIUM BLOCKCHAIN NETWORKS
On the other side of the “Trust continuum” described in Figure 1, we find the traditional centralized systems and the Private Blockchain Consortiums. Given the different trust requirements in those Private Consortiums, they can implement much more efficient consensus algorithms, without requiring mining and with low and predictable transaction costs.

## 4.1. A different “Trust trade-off”
In public-permissionless networks like Bitcoin or Ethereum, the transacting identities are anonymous (strictly speaking they are pseudonymous, but in practice most of them do not know each other so we can assume they are anonymous), so the task of the system is to achieve with an adequate level of trust that the transactions are valid and that each party will comply with its duties. This is a very difficult task to perform in these conditions, and this is mainly the reason for the poor throughput observed in those public permissionless networks.
 
In private consortiums, the entities transacting have well-known identities, and they are subject to compliance to the law and to regulation. That means that there are lower requirements on “Trustless”, because system trust can be complemented via external mechanisms to the blockchain network. For example, it is expected that at the beginning of the adoption of blockchain technology, the on-chain transactions are covered by standard agreements negotiated and signed in the off-chain world.

The objectives of using blockchain technology in a consortium are normally different than the objectives in a public-permissioned network of unknown participants. Rather than allowing operation among anonymous participants and being able to resist attacks from unknown malicious actors, the main benefit of blockchain technology in a consortium is to make more efficient the operation of the consortium without having to resort to, for example, a Joint Venture to which every participant would have to connect just for technical reasons.

The blockchain technology allows all parties to securely share data and transactional information in a way that avoids costly reconciliations. There are normally very strict governance rules that regulate the sharing of data and ensure the legal enforceability of the transactions that are recorded in the ledger.

By using blockchain technology, entities know that all transactions are, if required, fully traceable and can be easily audited ex post facto, so their incentives to cheat and commit fraud on the blockchain are very low, and in any case could be resolved applying the very well defined governance mechanisms of the consortium or, in extreme cases, via the standard legal mechanisms.

This property of traceability and ex post facto auditability should be enabled by the technical property of “immutability of blockchain data”. In the real world, immutability is not an absolute property, that is, in practice there are degrees of difficulty to modify the data without being noticed.  The question then can be reduced to how to achieve a “good enough” degree of immutability while at the same time achieve sufficient performance and throughput to make the system practical.

In summary, relaxing the level of “system trust” required to function (because we can complement it with external trust among transacting partners), enables us to implement other consensus algorithms which are more efficient and provide greater throughput, while keeping safety at an appropriate level for the purposes of the consortium.

Even in some cases where there are high levels of trust among the participants and the network is secured from external actions, the consortium may decide to implement consensus algorithms which are just CFT ( Crash Fault Tolerant) like Raft, which are more performant than those which are BFT (Byzantine Fault Tolerant).

More details about consensus algorithms will be discussed in the corresponding section below.

## 4.2. A different incentivisation model for operating nodes
As mentioned at the beginning of the document, in a public-permissionless network there should be an economic incentivisation mechanism for promoting anonymous participants to dedicate expensive computing resources to execute the consensus algorithm required for the operation of the network and ensuring safety.

In those networks the reward system is designed to be extremely short-term, that is, on every block creation event the miner or validator gets rewarded in the cryptocurrency that the network uses. Depending on the actual implementation of the network (eg. PoW, PoS, digital currency units created at launch or not, …) the rewards could be different, but they all share the feature of being very short-term and anonymous (strictly speaking, pseudonymous).

In a private consortium the incentivisation to operate the nodes is completely different, changing to a traditional investment model. The participants in the consortium want to operate the nodes in order to obtain benefits on a longer-term basis. The benefits could come from reduced costs due to increased efficiency, from better service to their customer, or even from new products or services that could be developed jointly.

But in any case, there is no need to use the very short-term incentivisation employed in the public-permissionless networks, so in these blockchains there is no need for embedded cryptocurrencies in order to ensure participation and safety of the network.

This longer-term incentivisation mechanism brings two major benefits:
* The nodes are operated as traditional infrastructure, with low and predictable costs over time. There is not a requirement for transactions fees (unless the members decide to have them because this is their agreed business model). In any case, the costs do not have the highly speculative nature we see currently in public-permissioned networks.
* Allows to use consensus algorithms which are much more efficient and provide higher throughput, and still providing an adequate level of safety.

## 4.3 A different Transaction execution model
In general, in public-permissionless blockchain networks like Bitcoin and Ethereum there are essentially two mechanisms that ensure the safety property of the network:
1. All transactions are executed and validated in all participating nodes in a deterministic way.
2. There is a consensus algorithm used to ensure that all nodes agree on the same order of transactions, so they are executed in exactly the same order in all the nodes.

For example, in Ethereum the transactions are first validated (via their execution) in the miner/minter nodes, the one node that wins the cryptographic lottery decides the order of transactions in the block, and then all the other nodes in the network execute all the transactions in the block in the order specified by the winner. This is referred to as the “order-execute” model.

Indeed, the existence of an algorithm to reach consensus on the order of transactions is not exclusive to public-permissionless networks and is required in all types of blockchain networks,  though they may differ in the implementation.
However, in private consortiums and in order to achieve privacy, among other things, it is not required that all transactions are executed in all nodes of the network.

For example, in Quorum, private transactions are only executed in the nodes which are privy to the transaction (those specified in the “privateFor” parameter). In addition, the payload of private transactions is only stored in those nodes and is never sent or replicated to any other node in the network, and private transactions can only modify the so-called “private state” which is different in each node and depends on the actual private transactions where each node has participated. Public transactions in Quorum follow exactly the same model as in standard Ethereum.

In contrast to public state, safety of private state data can only be ensured indirectly: even though private transactions are executed in just a reduced number of nodes in the network, the transactions are included in the blocks that are stored in the blockchain in all nodes. The transaction in the block does not include the payload nor the transaction results. A node that did not participate in the private transaction can not verify the transaction by executing it, but all nodes that did participate in the transaction can replay it and given the deterministic nature of the EVM, they can asume that if the initial states were the same

# 5. ALASTRIA: A PUBLIC-PERMISSIONED BLOCKCHAIN NETWORK
![Alastria in the Trust Continuum](/assets/Alastria%20in%20the%20Trust%20Continuum.jpg)
<p align="center"><b>Fig2. - Alastria in the Trust Continuum.</b></p>

***

In Public-Permissioned networks, the objective is to maximize decentralization and safety, even if this goes to the detriment of scalability. In this context, decentralization typically means the ability to transact anonymously but safely among individuals without the need for any intermediary acting as trusted party. It is often the case that the requirement to eliminate third parties is stronger than the requirement that the system be high-performance so it could be used as a general purpose transaction mechanism.

In Private Consortiums the objectives are generally different, and instead of trying to eliminate third parties at all costs, they try to use blockchain technology to improve efficiency and reduce costs of transaction among the partnets composing the consortium. In many private consortiums, they want a shared database and transaction system so they can eliminate frictions and reduce costs of reconciliation.


As Figure 1 and Figure 2 describe, Alastria tries to be as public as possible, but without the disadvantages associated with public-permissionless networks.

As mentioned before, Alastria is not a Private Consortium but instead is a Public-Permissioned network compatible with regulation (more on this later). At a very high-level, the characteristics of Alastria are the following:
* It’s permissioned, so every participant node has to be identified before it can participate in the network
* No cryptocurrency embedded
* A more efficient consensus algorithm, enabling higher performance and scalability
* Transaction finality in one block, enabling legal validity of executed transactions
* Implements legal identities of all participants

# 6. GENERAL REQUIREMENTS ABOUT THE SOFTWARE
## 6.1. Based on OpenSource of wide acceptance in the market
This is in order to minimize as much as possible any dependencies on any specific vendor. In particular:
1. Alastria will not develop its own blockchain software, but will use a widely used one.
2. Alastria will not incorporate any proprietary components or force to the members to use any proprietary component.
3. The software used by Alastria should be built by an Open Source community as wide and as diverse as possible.

## 6.2. The ecosystem of users of the software should be as wide as possible
This is in order to minimize the risks of using software that will stop being developed in the future. It also makes sure that the innovation rate is high and is also evolving rapidly. In particular:
1. The ecosystem of developers using the software should be as wide as possible.
2. The ecosystem of applications using the software should be as wide as possible.
3. The ecosystem of knowledge about the software should be as wide as possible.

## 6.3. Alastria should be based on general-purpose and multi-industry platforms
Alastria has to support all the different use cases that can appear in a multi-industry country blockchain network, so Alastria will avoid any software which is specific to one industry or is too specialised. That means that there may be some very specialized use cases that are not supported directly by Alastria, at least at the beginning. The challenge here is to be able to interoperate between different blockchain networks. One possibility being actively investigated is the ability to run in parallel two (or more) blockchain networks with different technology, to be able to support a wider spectrum of use cases.

## 6.4. Alastria will allow and facilitate regulatory compliance by the members, in particular:
(The list is in Spanish because we are currently focusing on the specific problems of Spanish regulation).

1. Reglamento General de Protección de Datos (RGPD)
2. Ley de Servicio de Sociedad de la Información y Comercio Electrónico (LSSI)
3. Reglamento de prevención del blanqueo de capitales y de la financiación del terrorismo
4. Normas y recomendaciones del Consejo Nacional de Ciberseguridad

The next section introduces a proposed reference architecture for blockchain systems or DLTs in general (in line with the Reference Architecture being developed in the ISO TC-307) and after that we will discuss the detailed requirements and challenges that a networks like Alastria has to solve.

# 7. REFERENCE ARCHITECTURE OF A BLOCKCHAIN
The reference architecture of blockchain and distributed ledger technology consists of five layers, as well as a cross-layer feature set across the layers. They are depicted in the following diagram, and the next sections describe the layers and each of the individual components.

![Reference architecture of a DLT](/assets/Reference%20architecture%20of%20a%20DLT%20-%20overall.jpg)
<p align="center"><b>Fig3. - Reference architecture of a blockchain.</b></p>

## 7.1. Infrastructure layer
The Infrastructure layer provides the operating environment, including networking, compute and storage components required for the normal operation of a blockchain system. It may be provided as a set of cloud computing resources or it may be provided as on-premises equipment.

### 7.1.1. Data Storage
Physical location to put data for the ledger and other data store requirements. Data Storage function should meet the following requirements:

* can be deployed and used by each node in the peer-to-peer network
* can be deployed distributed or local
* can support appropriate data sovereignty, given that network nodes are in general run and managed by different legal entities
* can provide data writing and query services efficiently, safely and stably
* can provide enough storage space for the growing requirements of the ledger as transactions accumulate with time

Given the characteristics of blockchain systems, probably the most important requirement for the Data Storage function is the sizing requirements in order to support the storage of the historical data for the ledger.

Full nodes typically require the storage of the whole history of the blockchain including the genesis block. Other types of nodes may require less storage, if they assume some reduction in trust for block validation, as it can not be performed against the whole history of the ledger.

These are the associated requirements for the Quorum implementation of Alastria:

| Ref     | Requirement                                           |
|---------|-------------------------------------------------------|
|STOR_001 | What are the storage requirements of Validator nodes? |
|STOR_002 | What are the storage requirements of Regular nodes?   |
|STOR_003 | What is the recommended checkpointing policy in order to reduce the size of the blockchain data, while keeping an appropriate level of trust in the data? |

### 7.1.2. Runtime Environment (Compute)
The Runtime environment function provides the execution capabilities (CPU, memory) for the operation of the blockchain system, including but not limited to container technology, virtual machine technology and cloud computing technology. Generally, runtime environments should be provided to each node in the blockchain system.

In general, the fastest the machines of each node in the network, the faster the consensus algorithm can run and he greater the throughput of the network. However, Alastria is starting with Quorum, and in Ethereum-based public-permissioned network like Alastria, some care should be taken on this subject.

In Ethereum, all nodes execute the Smart Contract code associated with all transactions, and the same happens for public transactions in Quorum. In a network running with the IBFT consensus algorithm, a very big throughput on the validator set may require bigger machines in the Regular nodes, to keep up with the network. In other words, it could happen that a given regular node can not execute transactions and commit blocks at the speed at which the validator set generates blocks.

| Ref     | Requirement                                                  |
|---------|--------------------------------------------------------------|
|COMP_001 | What are the CPU and memory requirements of Validator nodes? |
|COMP-002 | What are the CPU and memory requirements of Regular nodes?   |

### 7.1.3. Communication Networks
Communication networks are required for the peer-to-peer networking of the DLT system nodes and also for communication between the DLT system and the entities in the user layer and in the non-DLT systems.

Given the network architecture of Alastria, the throughput of the consensus algorithm (IBFT) may be highly dependent of the latency of the communication links among the Validator nodes.

Having dedicated lines would increase throughput, reduce latency and minimize asynchrony. A very well inter-connected validator set may allow heuristics to be applied for much faster consensus algorithm execution. Another example could be using duplicated communication hardware in the validator nodes, which allows for using one card to talk to peer validator nodes and the other card for the rest of the nodes in the network. This way, the validator subnet would be dedicated, and could be protected from DoS attacks.


| Ref     | Requirement                                                  |
|---------|--------------------------------------------------------------|
|COMM_001 | What is the physical architecture of the communications network among validator nodes and what are the minimum requirements for speed, latency and reliability of the communication links among the Validator nodes? How does it affect the consensus algorithm, specifically to the ability of configuring low block making times? |

## 7.2. DLT Platform layer
The DLT Platform layer contains the core functions of the DLT system that can run in a DLT node and which also involves communication between nodes. Key capabilities include:

* Consensus mechanisms which coordinates the data and account records in the ledger between nodes. This consensus mechanism lays the foundation of the DLT system and is probably the function that affects the most to the resulting properties of the the DLT system.

+ Communications between DLT nodes and perhaps systems via events and secure protocols.
Crypto services functions which includes privacy protection, encryption, digital signature and other capabilities to ensure security compliance and tampering resistance of the DLT system.

* Smart contracts running in a secure runtime, that implement the logic running inside the DLT system and updating the ledger data.

The DLT Platform layer connects hardware or network infrastructure provided by the Infrastructure layer, to relevant functional support services in the API layer. In detail, the capabilities supported by the DLT Platform Layer includes:

* Secure runtime
* Smart contract
* Ledger
* Transaction System
* Membership Services
* State Management
* Consensus Mechanism
* Event Distribution
* Crypto Services
* Secure Inter Node Communications

### 7.2.1. Secure Runtime
During runtime, a transaction may invoke smart contract functions requiring a secure environment. A secure runtime environment is a hosting environment for server-side DLT business logic.

Different DLTs use different Secure Runtime technologies. For example Ethereum (and so Quorum) uses a Virtual Machine (VM) implementation where all the logic is executed. Hyperledger Fabric uses Docker containers, while others use special hardware to ensure the properties of DLTs and implement a so-called Trusted Execution Environment, or TEE.

For software-based runtimes in a public setting (whether permissionless or permissioned), the runtime should be protected from rogue Smart Contracts or even malicious ones. One mechanism is running the logic inside a metered VM, like in Ethereum or Quorum.

On the other hand, running Smart Contract code inside a container running at native code speed like in Hyperledger Fabric, may be the right approach for private consortiums where the number of nodes is relatively small and the entities are very well known among them, and the code is normally common among all entities and it is certified and tested by all of them.

### 7.2.2. Smart Contract
A Smart contract is a distributed application running on and distributed with the distributed ledger. It represents more the process of agreeing on an outcome than its legal status. Its outcome may or may not be legally binding.

Smart contracts (also termed chaincode, programmable asset or programmable contract) are instantiated as computer programs that execute in a Secure Runtime within the DLT platform of any node in the DLT system, when a user sends a transaction of a particular type to the DLT system.

### 7.2.3. Ledger
A ledger is an information store which keeps a final and definitive record of (business) transactions. A ledger includes data store capabilities. Data Storage function supports writing and query of various types of data, generated during the operation of the DLT system, such as the ledger, transaction information, etc.

The technical implementation of the ledger is often an embedded key-value database, but it can be a  relational database, an external key-value pair database, a file database, and so on. It should support data fragmentation and routing capabilities where database sharding is supported.

Some DLT systems allow the ledger database to be queried externally using the standard tools for that database as they are used in any other type of application.

### 7.2.4. State Management
The state management component keeps track of the state of assets which are held on the DLT system, updating that state when new transactions are committed to the ledger.

Normally, the contents of the  state data are not stored in the ledger, but instead the ledger is used to store transactions and pointers to the state data, which is kept separate. The state data is “notarized” in the ledger using hashing technology (usually Merkle Tries).

In the case of Quorum and in order to support privacy, there are two sets of state data: the Public State and the Private State.

Public State is notarized in the ledger and so it is ensured to be globally consistent across all nodes at all times.

However, the Private State may be different across the nodes, depending on which Private Transactions each node has participated on. The assurance of consistency for Private Transactions has to be implicit.

First, the ledger (which is always globally available) stores the hashes of the Private Transactions that have been executed in the corresponding nodes and that have modified the Private State on the nodes which have executed them (each node executes only the transaction to which the node is a party, and not the others).

Thanks to the deterministic property of the transaction execution of the virtual machine, the Private State of each participating node can be implicitly determined to be consistent across the participating nodes, because the modifications to the Private State made by each transaction must have been exactly the same for all nodes executing the transaction.

### 7.2.5. Transaction System
The transaction system is the component that manages the addition of transactions to the ledger.

### 7.2.6. Membership Services
Membership Services are services that manage the identity, privacy, confidentiality and auditability within the DLT system. Membership services only apply to permissioned DLT systems, like Alastria.

In public-permissionless blockchain networks, everything revolves around accounts, which are the entities that can initiate and receive transactions. Given the decentralized philosophy of the system, it is very natural that the transactions and the ledger only store information about the accounts that participate in the transactions, and not, for example, about the actual node that initiated the transaction. In this sense, all nodes in these networks are equal and are just a technical mechanism to participate in the network, much in the same sense as the routers that handle communications among the participants, whose identity is not relevant to the blockchain upper layers.

However, in Alastria and other permissioned networks, we require the management of the identity of the nodes that are being operated by the participants, and that are used to initiate the transactions.

A proper membership service should account for the management of all relevant resources in the network, and that includes the nodes, which have to be permissioned and monitored for compliance to the policies of the consortium. In Quorum, there is a very basic mechanism of permissioning which may be good enough for Private Consortiums, but it needs enhancement for a Public-Permissioned network like Alastria.

Currently, node permissioning is managed via a file that is stored in each participating node and is reloaded and checked every time a new connection request is received in the P2P communications layer. This mechanism has two main disadvantages:

1. Currently, an Alastria participating entity can modify the permissioning file and add the node identities of other entities that are not part of Alastria. Once those non-Alastria entities have their nodes communication directly with the non-compliant node, thanks to the P2P communication protocol of Quorum, they have access to the whole network.
2. Eliminating a node from the permissioning list requires modifying the permissioning file and restarting the node. This implies that eliminating a node from the network requires a restart for all nodes in the network. 

These challenges are formalized as requirements in the following table:

|Ref      | Requirement                                                   |
|---------|--------------------------------------------------------------|
|MEMB_001 | We require a node permissioning mechanism which can not be modified arbitrarily by participating entities.                                   |
|MEMB_002 | We require an un-permissioning mechanism that is dynamic and that does not require a restart of all the nodes in the network.                       |

### 7.2.7. Consensus Mechanism
Consensus is a set of rules and procedures that allow the DLT system to maintain and update the distributed ledger and to ensure the trustworthiness of the records in the ledger, that is, their reliability, authenticity and accuracy (this is often referred to as safety). Consensus mechanisms are implementations by which consensus is achieved in DLT systems. There are many alternative consensus mechanisms in use in different DLT systems. Examples of consensus mechanisms include Delegated Proof-of-Stake, Paxos algorithm, Practical Byzantine Fault Tolerance, Proof-of-Authority, Proof-of-Burn, Proof-of-Capacity, Proof-of-ownership, Proof-of-stake, Zero knowledge proof, Proof-of-work.

The current implementation of Quorum in Alastria uses the Istanbul BFT (IBFT) consensus algorithm, and as it is a variant of PBFT its behaviour isf very well documented.

For a Public-Permissioned network like Alastria, IBFT seems much better suited than the current algorithms used (or planned) in public-permissionless networks like PoW or even PoS. The efficiency and transaction throughput that can be achieved are much greater than with those required in public networks. In addition, transaction finality can be deterministic which is a requirement for facilitating legal commercial transactions.

This higher efficiency and throughput in IBFT is achieved by using a reduced set of Validator nodes which are the ones running the consensus algorithm. These nodes are the only ones in the network that decide the blocks in the ledger and which transactions are included and in which order. The rest of the network (Regular nodes), receive the blocks created by the Validator nodes and apply them to the blockchain (of course, after executing and validating the transactions included in the block).

In a Private Consortium, this approach works very well, because it is typically formed by a small number of entities that are very well-known to each other, so the “trustless” requirements are not as high as in public-permissionless networks. In small consortiums, all entities could even run Validator nodes and so the operation of the network is truly decentralized.

For a large Public-Permissioned network like Alastria, there are however some challenges that require novel solutions to them, all revolving around the compromises required to achieve an acceptable throughput but at the same time obtaining a “good enough” level of trust on the system (refer to Figure 2 above).

#### 7.2.7.1. Trust and Validator nodes in IBFT
The whole network, composed of many entities operating Regular nodes, have to trust that the set of Validator nodes perform their duties as expected. Basically, the entities of Alastria do not necessarily have to trust on each and every of the individual entities running the Validator nodes, but instead they have to trust that the Validator nodes will not collude and collaborate among them to take decisions that will affect adversely to the rest of the nodes (either to individual nodes or to a set of them).

That is, there may be some validator nodes that are not fully trusted by a given entity of Alastria, but if those are less than ⅓ of the total number of Validator nodes, then the whole set can be trusted to perform their duties.

From the point of view of decentralization, this situation is much better than having to rely on a single centralized entity, but nonetheless is less “trustless” than a public-permissionless network. This makes the process of selection of Validator nodes not just a technical one, but a very critical one for the proper functioning of the network and being able to reach the right level of “trustless”.

#### 7.2.7.2. Selection of Validator nodes
For the above reasons, the process of selection of Validator nodes should be decentralized and avoid concentration of power in any single entity or on a reduced group of entities. For example, the set of Validator nodes should reflect diversity across industry sectors and geographies.

| Ref   | Requirement     |
|---------|-------------------------------------------------------------------|
|CONS_001 | What is the policy for determining the entities that operate Validator nodes in Alastria. The technical and operational requirements are not enough, and Alastria needs an additional “political” policy. For example, it would not be desirable that all validator nodes are banks, as this could undermine the trust of the rest of the nodes in the true decentralized properties of the network. That is, diversity has to be maximized and the probability of collusion minimized, while complying with the technical and operational requirements. Additionally, if for example the optimum number of validator nodes is 20 and we have more than 20 entities willing to be a validator node, what is the policy for selecting just 20? As another example, if a better suited validator node (for “political” reasons) asks at some time to become a validator, do we replace an existing one? What is the policy for doing the selection?                     |
|CONS_002 | What are the technical requirements (sizing for CPU, memory, disk) for the Validator nodes. In general, the fastest the machine, the faster the consensus algorithm can run and greater the throughput of the network. However, a very big throughput on the validator set may require bigger machines in the Regular nodes, to keep up with the network. In other words, it could happen that a given regulator node can not execute transactions and commit blocks at the speed at which the validator set generates blocks. |
|CONS_003 | What are the operational requirements for validator nodes? In other words, what are the SLA requirements that entities operating validator nodes have to comply with? This should include procedures and policies to execute when a validator node is detected not working too many times (expulsion and reincorporation to the validator set, off-chain notification and escalation processes, etc).                       |

#### 7.2.7.3. Number of Validator nodes

| Ref     | Requirement                                                       |
|---------|-------------------------------------------------------------------|
|VALID_001 | What is the right number of Validator nodes that Alastria should use? For example, the minimum number for having some BFT protection is 4, and this maximizes performance, but provides the minimum level of safety and decentralization.   |

### 7.2.8. Event Distribution
The event distribution component handles the distribution of events generated within the DLT platform. An example is an event generated by the execution of a smart contract, which might be used by a user application to signal the completion of a transaction to the end user.

### 7.2.9. Crypto Services
The Cryptographic Services component provides the DLT system with access to the necessary cryptographic algorithms, either directly or by providing an interface to hardware or software that implements the algorithms. Hash functions and digital signatures are examples of algorithms that are commonly used in DLT systems. Hash functions are often used to protect the ledger from modifications. Any change to information in the ledger will result in a computed hash that is different from the hash that was previously computed and stored for the ledger. A new hash is computed each time a transaction is added to the ledger. Digital signatures ensure that the receiver receives the transactions without intermediate parties modifying or forging the contents of transactions, while also ensuring that the transactions originated from senders (signed with private keys) and not imposters.

### 7.2.10. Secure Inter-Node Communication
The secure inter-node communication component handles communication between nodes over the network, enabling the operation of the distributed ledger. The inter-node protocol, also called the backbone protocol runs via this component.

## 7.3. API layer
The API layer contains functions that provide reliable and efficient access to the DLT system for applications, users and non-DLT systems, by calling functional components in the DLT Platform layer, and provides unified access and node management. The API layer can enable increased performance by facilitating efficient cache, reliable storage, load balancing, and provide users with reliable and efficient access capabilities. We can distinguish three different types of APIs.

### 7.3.1. External Interfaces
Off-chain access services provide secure means to access capabilities outside the DLT system such as trusted data sources or functions.

### 7.3.2. User API
Application programming interface that provides access to domain specific function meant to accomplish some business purpose (for the business user).

### 7.3.3. Admin API
Application programming interface that provides access to administrator and operator functions.

## 7.4. User layer
User layer contains functions to enable DLT customers to interact with DLT functions, DLT operators, and administrative functions. User layer can also communicate to other layers to provide support for DLT cross-layer functions.

### 7.4.1. User Applications
User Applications are applications which run separately from the DLT systems that acts as a client to the DLT system, used by users, usually to perform domain specific or applications specific functions.

### 7.4.2. Administration Applications
Administration Applications are applications which run separately from the DLT systems that acts as a client to the DLT system, used by administrators supporting capabilities to maintain and/or update applications and systems.

## 7.5. Non-DLT Systems Layer
The non-DLT systems layer contains systems outside the DLT system that a DLT system communicates with in order to accomplish its business goals. This includes:

### 7.5.1. DLT Oracles
A DLT oracle is a trusted service designed to supply external data to a DLT system. It is out of scope for this document to describe in detail the operation and integration of oracles in the DLT system.

### 7.5.2. Non DLT Applications
Non-DLT applications are any applications outside the DLT system with which the DLT system communicates, either to send or receive data. An example is a Core Banking System connected to a Smart Contract that tokenizes fiat money.

### 7.5.3. Off Ledger Data
Off-Ledger data is any data store outside the DLT system that can hold data that relates to the DLT system in some way. An example might be a database holding additional data relating to transactions held on the ledger. Off-Ledger Data is a critical component needed to implement proper data privacy functions.

## 7.6. Cross-layer functions
The cross-layer functions support the components across all the functional layers. For example, security is needed for user layer, API layer and DLT Platform layer, therefore security is a cross-layer functional component. Cross layer functions can support other cross layer functions as well. The functions are grouped into Development, Operations & Management, Security, and Governance & Compliance categories. The cross-layer functions are depicted in the following figure and are described in more detail in the following sections.

![Reference architecture of a DLT](/assets/Reference%20architecture%20of%20a%20DLT%20-%20cross%20layer.jpg)
<p align="center"><b>Fig4. - Cross layer functions in a blockchain.</b></p>

### 7.6.1. Development
Development functional components support the activities of DLT system developer, including application and system implementation development, build management and test management.

#### 7.6.1.1. IDE (Integrated Development Environment)
IDE functional components provide tools for the development of smart contracts, DLT and related applications, including development of support modules. IDE functional components support the use of capabilities provided by DLT operator, including access via APIs, node management and event distribution capabilities. IDEs enable use of functions in the API of the DLT platform layer, as well as the infrastructure layer. The IDE component supports the generation of configuration-related configuration metadata for the development of the smart contract; supports the preparation or generation of smart contracts configuration scripts and components used by the operators and nodes operating systems.

#### 7.6.1.2. Build Management
Build management functional components are used to build publishable software packages. The package can be submitted to DLT node owner or operator and deployed in production environment. It contains both the software for smart contract implementation and the configuration metadata and configuration scripts. Build management features include:

* support for automated building software packages function
* provide automated compilation function
* provide an error message when an error occurs during the build process
* implement audit during build process
* build system that provides multi-language support

#### 7.6.1.3. Test Management
Test management functional components support testing of all functions of DLT systems. The components should generate test reports and provide them with system implementation software to the node owner or operator. In general, test is performed in a special independent test environment, which should be a simulation of production environment. Without affecting production, test work can also be carried out in a production environment. A test environment should be provided by DLT operator or partner.

Test management functional components should include at least the following functions:

* test management components should support the management of test plans, test reports, test cases and so on
* support automatic generation of test reports
* when test is conducted under the integration of test environment and production environment
* production environment should not be affected
* support testing process automation
* provide test case library, test database management functions

### 7.6.2. Management and Operations
Management and Operations functional components include a set of operational-related management functions, which are used to manage and control DLT capabilities provided to user. Management and Operations functional components include:

* service directory
* incident management
* delivery management
* node management
* ledger management
* monitoring
* update and version management

#### 7.6.2.1. Service directory
Service directory function provides a list of all DLT capabilities, smart contracts, services and/or APIs of a particular DLT system, operator, or node. The list includes / refers to technical information about deployment, provision and operation of DLT smart contract, service or API.

#### 7.6.2.2. Incident Management
Incident management function provides the ability to capture incident and problem reports, and manage them through analysis. Incident and problems can be detected and reported by DLT node or DLT operators or DLT user.

#### 7.6.2.3. Delivery Management
Delivery management function provides the management function of DLT system delivery, which is provided in the forms of system implementation and access endpoint. At the same time, this function provides necessary workflows to ensure the elements are provided in correct order

#### 7.6.2.4. Node Management
Node management function provides management of the DLT platform node implementation including performance and availability usually on one logical or virtual system

#### 7.6.2.5. Ledger Management
Ledger Management function provides management of the distributed ledger

#### 7.6.2.6. DLT System Management
DLT System Management function provides management of DLT systems especially for performance and availability

#### 7.6.2.7. Monitoring
Monitoring functions include monitoring, analytics, and automation tools that are used to respond to some changes in the platform and environment. This could include responding to changes in the required system capacity and error analytics.

Alastria has implemented a first version of a distributed monitoring tool that reports on different parameters of each node of the network. For example, the monitoring tool checks for compliance to the permissioning policies of all nodes in the network.

| Ref      | Requirement                                              |
|----------|----------------------------------------------------------|
|MONIT_001 | Validate (or otherwise suggest another option) that the current network monitoring tool implemented in Alastria can be used for the short term and suggest improvements to make it better.                                       |

#### 7.6.2.8. Update and Version Management
Update and version management functions include management of code bases and implementation artifacts for the nodes and DLT systems

### 7.6.3. Security capabilities
The function of security layer is mainly to provide security attributes such as authentication, authorization, confidentiality, integrity and accessibility for all the functional layers of the DLT RA and the protocols between nodes. These security features are widely used in user and node identity authentication, transaction protocol design, chained data organization, communication channel encryption, and application data access control. The Security layer includes the following functions:

* authentication and identity management
* security policy management
* access management
* PII protection

#### 7.6.3.1. Authentication and Identity Management
The authentication and identity management functions provide user’s identity verification process to determine whether the user has access and usage rights to a resource, thereby enabling the DLT system access control policy to be performed reliably and efficiently. The authentication and identity management functional components include the following features:

* support the establishment of identity management strategy, determine whether certification is based on user-known information, user-owned information or user's unique physical characteristics
* support the use of specific identity authentication methods to support identity management policies
* support the establishment of user identity management mechanisms based on identity authentication

#### 7.6.3.2. Security Policy Management
The security policy management functions provide permission for users to access to or use a resource, and develop a set of rules that must be followed by all security-related activities in a secure area. Security policy management functional components include

* function to authorize users to access and use resource
* function to set authorization and security rules
* functions that authorization and security rules are controlled by security authority

#### 7.6.3.3. Access Management
The access management component is used to provide control over access to specific capabilities of the DLT system. This can include access controls applied to the various interfaces in the API layer.

#### 7.6.3.4. PII Protection
The PII protection component provides capabilities to assist the provision of appropriate protection to any PII handled by the DLT system. This can include identification and classification of the PII, the application of encryption, the management of lifecycle for PII (including early deletion of any PII no longer required), providing access to PII for data subjects

### 7.6.4. Governance and Compliance
Governance and Compliance functional components enable the DLT system to conform to governed and auditable characteristics based on governance and compliance requirements of DLT node owners and operators. Governance can help prevent DLT networks from being outside of laws, regulations and industry rules (like becoming the carrier of money laundering, illegal financing or criminal transactions). They include the following functions:

* supervisory support
* audit support
* governance control
* policy management

#### 7.6.4.1. Supervisory Support
Supervisory support function is mainly used to meet the requirements of supervisory bodies for environment, system, availability, disaster recovery, system operation and maintenance, and compliance of supported functions in DLT system. Due to differences between industry supervisors and supervisory methods, the depth and breadth of functions involved are different. Specific needs include:

* should have a sound and complete supervisory governance system. Through pre-admission control, in-process authority control, ex post facto and other technical means to achieve supervisory objectives, ensure that records cannot be tampered with, be traceable and auditable.
* let supervisory bodies join the DLT network as one of the nodes for immediate supervision. The supervisory node can monitor and audit data integrity, validity and process compliance in real time, intervene in transaction, and stop illegal business. In the case of Quorum, there should be a process for the supervisory entities to get the data of private transactions.
* data and evidence related to supervision and intervention activities should be recorded and maintained
* set clear supervisory governance rules. Support rules that are supervised and managed by people and cannot be automatically implemented by technology
* support rules for the organization or management personnel to conduct supervisory governance in accordance with laws, administrative regulations, departmental rules and regulations, encourage full use of smart contracts and other technologies to effectively support intelligent supervisory operation, and provide supervisory rules for automated implementation
* save data and evidence relating to systems, resources and performance. These data and evidence include records and logs of all participants' activities and operating environmental conditions, which need to be collected and maintained in a safe manner

#### 7.6.4.2. Audit Support
Audit support function is mainly used to achieve audit internal control, responsibility identification, event traceability and other requirements of DLT system, which needs effective technical means together with business sector standards for accurate audit management. Specific requirements include:

* enable conducting pre-audit, concurrent audit and post audit on DLT activities, establish audit indicators such as violation of discipline audit, internal control system audit, performance audit and other contents
* enable DLT auditors join the DLT network as one of the nodes for real-time audit, or allow the DLT auditor to access to data and evidence in DLT networks on demand or on a regular basis as a third-party outside the DLT network. Encourage non-tampering and traceable characteristics based on DLT technology, make real-time verification on records of audited object and use as audit evidence
* enable docking and interactions between DLT networks and other related systems, improve audit efficiency and reliability of audit results
* enable data and evidence related to audit activities. The data and evidence include but are not limited to records and logs of activities and operating environment conditions of all participants in DLT, audit view record of the auditor, audit processes and results information, and avoid leakage of audit information

#### 7.6.4.3. Governance Controls
Controls communications of policies and notifications of policy violations and escalation processes for exceptions and grievances.

#### 7.6.4.4. Policy Management
Policy management function provides definition, update and access policies for DLT systems and their management. These policies include DLT systems itself and its business, technology, security, privacy, and authentication. Management of policies at all levels of the distributed systems
