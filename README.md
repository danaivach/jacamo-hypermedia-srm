# JaCaMo-hypermedia

This project implements a [JaCaMo](https://github.com/jacamo-lang/jacamo) bridge for [Yggdrasil](https://github.com/interactions-hsg/yggdrasil).

## Prerequisites

- JDK 8+

## Getting started

Clone this project with:

```
git clone --recursive git@github.com:Interactions-HSG/jacamo-hypermedia.git
```

Run `./gradlew`

## AAMAS 2024
This repository holds the JaCaMo application that executes the experiments outlined in the paper titled "Enabling BDI Agents to Reason on a Dynamic Action Repertoire in Hypermedia Environments", presented in AAMAS 2024.
The implementation uses the following libraries:
- [hMAS-java](https://github.com/danaivach/hmas-java): A Java library for reading, writing, and interacting with resources based on the [Hypermedia MAS Ontology](https://purl.org/hmas/core).
- [signifier-resolution-mechanism](https://github.com/danaivach/signifier-resolution-mechanism/tree/main): A Java implementation of a Signifier Resolution Mechanism (SRM), which resolves abstract actions of pre-defined AgentSpeak plans to concrete actions signified in the environment at run time. The SRM implementation overrides the native _option selection function_ of the Jason reasoning cycle [1].

The application deploys Jason agents, where each agent uses a different version of an SRM. Each agent exhibits different behavior by performing signifier resolution according to different criteria:
|                 | Action Availability | Satisfaction of Recommended Context | Satisfaction of Recommended Abilities |
|-----------------|---------------------|-------------------------------------|---------------------------------------|
| Agent A (Alice) |  &#x2612;           |  &#x2612;                           |  &#x2612;                             |
| Agent B (Bob)   |  &#x2611;           |  &#x2612;                           |  &#x2612;                             |
| Agent C (Carol) |  &#x2611;           |  &#x2611;                           |  &#x2612;                             |
| Agent D (David) |  &#x2611;           |  &#x2611;                           |  &#x2611;                             |

[1] Bordini, R. H., Hübner, J. F., & Wooldridge, M. (2007). Programming multi-agent systems in AgentSpeak using Jason. John Wiley & Sons.
