## Preamble

    AIP: `AIP-3`
    Title: `Node monitoring orchestration`
    Author: `Eduardo Sánchez`
    Type: `Monitor`
    Status: `Draft`
    Created: `25-01-2017`


## Description

The monitoring orchestrator tool must be able to track metrics from the nodes participating in the Alastria network, perform analysis, trigger automatic and manual tasks, while taking into account the constraints in the network.


## Motivation

While there is [another proposal to develop a monitoring application for Alastria nodes]( alastria-platform/AIPs/aip-2/aip-2.md ), managing all those nodes in fast growing distributed network in an isolated fashion does not scale. There is a need for a single point to coalesce metrics, perform metrics and schedule administrative tasks.

## Specification

Proposed User Stories:

1. As the Alastria core technical team, I want to confirm the availability of any node.

2. As the Alastria core technical team, I want access to monitor metrics for any node.

3. As a node administrator, I want to login using my Alastria credentials and then check the availability of my nodes.

4. As a node administrator, I want to login using my Alastria credentials and then access to monitor metrics for my nodes.

5. As the Alastria core technical team, I want to be able to shutdown any faulty node

6. As a node administrator, I want to login using my Alastria credentials and then be able to shutdown my node.

7. As the Alastria core technical team, I want to rotate the validator node list at regular intervals.

8. As the Alastria core technical team, I want to schedule node restarts, launching notification to node owners and observing consensus rules.

9. As the Alastria core technical team, I want to observe github webhooks, and schedule unnattended administrative tasks accordingly.

10. As the Alastria core technical team, I want to have a dashboard with alarms that are triggered by node metrics.

11. As the Alastria core technical team, I want to schedule manual or automatic actions in response to alarms.

12. As the Alastria core technical team, I want to perform a health-check to nodes at a designated intervals.

<!--
Repository: https://github.com/alastria/monitor

Go version: >= 1.3.
RESTFUL API - BeeGo: https://beego.me/
-->

## URL forum discussion

TBD
