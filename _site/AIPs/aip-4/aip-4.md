## Preamble

    AIP: `AIP-4`
    Title: `Identity Smart Contract enhacement`
    Author: `Iñigo Garcia`
    Type: `Identity`
    Status: `Draft`
    Created: `31-01-2017`


## Description

The Smart Contracts that support the Alastria Identity over the Alastria network should be adapted from the Uport ones, adding the new functionalities that Alastria ID needs like attestation acceptance & management, EIAS levels, and EIDAS recovery.


## Motivation

Some Alastria ID needs don't fit in any of the identity solutions that had been developed by the blockchain community. These solutions were designed in the most cases to work over public blockchains under the self-sovereign paradigm, including self-management and community attestation. In the Alastria ID platform participate government and corporate agents that allow for new interactions like user acceptance over attestations and new requirements as eIDAS level to support attestations to be legally binding.

## Specification

Proposed User Stories:

1. As a user, I want to make possible to create my identity in order to interact with the Alastria network.
2. As an identity owner, I want to make possible to provide my own attestations (EIDAS 0) with the aim of being able to complete my identity information.
3. As an identity owner, I want to make possible to manage links to my identity wallets with the aim of making access more flexible.
4. As an identity owner, I want to make possible to manage the identity with the aim of presenting identity claims as required by an Identity consumer.
5. As an identity owner, I want to make possible to ask for all the attributes of my identity with the aim of being able to manage my attestations.
6. As an identity owner, I want to make an authorized issuer (an EIDAS level 3 issuer or specifically authorized issuer) to (re)authenticate me, with the objective of recovering my lost identity.
7. As an issuer I want to issue attestations about an identity owner with an associated eIDAS level (within my level).
8. As an issuer I want to be able to withdraw or update an issued attestation for an identity owner.
9. As a identity owner I want to accept or reject an attestation and its associated eIDAS level from an Issuer
10. As an issuer I want to ask for a maximum eIDAS level, by attribute.
11. As Alastria I want to accept the required  Maximum eIDAS level for an issuer attestations, by attribute.
12. As AICT, I want to have contracts defined incrementally (Basic Identity Manager + Alastria Identity Manager) with the aim of making it easier to maintain.
13. As an AICT, I want to make my identity manager manage attestations with the aim of storing private identity information.
14. As an AICT, I want the external storage and format to be transparent for my identity manager.
<!--
Repository: https://github.com/alastria/alastria-identity
-->

## URL forum discussion
