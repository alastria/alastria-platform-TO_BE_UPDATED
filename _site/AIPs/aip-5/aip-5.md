## Preamble

    AIP: `AIP-5`
    Title: `Alastria infrastructure test environment`
    Author: `Alfonso de la Rocha`
    Type: `Core`
    Status: `Draft`
    Created: `06-02-2018`


## Description

We need an environmental setup to test enhancements, issues, bugs, errors,
or vulnerabilities over the platform without the need of changes over
the test-net or main-net, or without requiring nodes for changes or
specific information.


## Motivation
With the last fall of the network, we faced the problem that we do not
really know what was causing the problem. It is difficult and complex
to request every node in the network to replicate a specific state to
trace an issue. Therefore, in order to test enhancements, trace bugs
or replicate vulnerabilities, I propose the development of a test environment
to ease the replication of different scenarios over Alastria's infrastructure.

## Specification
Through the use of a set of Docker containers, we want to be able to easily
deploy a network with a specific number of validator nodes and regular nodes
to replicate scenarios over the infrastructure.
There will be a main Docker compose that to make custom deployments of
Alastria's infrastructure.

Additionally. different commands will be provided to
automatically replicate stress scenarios over the infrastructure:
- High traffic
- A number of validators nodes down
- Regular nodes misbehaving
- etc.

The preliminary version of this AIP will only include the Docker compose
for a basic deployment of an Alastria Infrastructure test environment,
adding scenario commands in the following versions.

Repository: https://github.com/alastria/test-environment
-->

## URL forum discussion
TBD