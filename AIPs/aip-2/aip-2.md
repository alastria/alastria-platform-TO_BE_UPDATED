## Preamble

    AIP: `AIP-2`
    Title: `Node monitoring`
    Author: `Marcos Serradilla`
    Type: `User History`
    Status: `Draft`
    Created: `11-01-2017`


## Abstract

Define the functionality that the Node Monitor utility should initially implement.

## Description

The monitoring tool must be able to maintain and update the infromación of the node by administrative needs of the network. 

Thus MIMO, collect monitoring information to identify possible overloads, modifications Indevid in the installation of the node, etc.

## Motivation

Some administrative operations on the node can be very repetitive and/or urgent to undertake, to expedite this whole process, it is proposed to develop an application that allows the technical team of Alastria to perform unattended operations along the Network.

## Specification

Proposed User Histories:

1. As a node manager I want to pre-authorize the execution of any of the commands that potentially allow to change something in my node.

2. As Alastria core technical team I want the configuration files to be updated in order to meet the demands of highs in the network.

3. As a Alastria core technical team I want to be able to confirm the update status of the configuration files in order to verify the status.

4. As a Alastria core technical team I want to be able to ask the administrators of the validator nodes to restart the Geth and constellation-nodes processes to be able to meet the demands of network outputs.

5. As a Alastria core technical team I want to be able to confirm the status of the Geth and constellation processes, including the date of the last release in order to meet the demands of network outputs.

6. As a Alastria core technical team I want the RPC API/API port to be accessed Cakeshop to obtain monitoring information in read mode.

7. As a technical team of Alastria I want that you can verify the version of the binaries and tools used to be able to request your update if necessary.

8. As a technical team of Alastria I want that when a pull on GitHub is done the relevant operation to be able to streamline the management processes.

9. As a Alastria core technical team I want you to be able to access the system monitoring information to get system performance information.

10. As a technical team of Alastria I want to have a console that integrates alarms to different situations that require attention in each and every one of the nodes of the system.

11. As Alastria core technical team I want to have a direct communication channel with the administrators of each and every one of the nodes through which to request specific actions and receive the corresponding answers.

12. As a Alastria core technical team I want to have a REST service with the access API both to launch the operations, and to obtain the monitoring information in order to automate the monitoring processes.

## Rationale

Repository: https://github.com/alastria/monitor

Go version: >= 1.3.
RESTFUL API - BeeGo: https://beego.me/

## URL forum discussion

TBD