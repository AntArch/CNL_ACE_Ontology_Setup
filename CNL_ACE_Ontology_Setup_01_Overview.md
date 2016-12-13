# CNL ACE Ontology Overview

This project is concerned with setting up environments that generate an [ontology](https://en.wikipedia.org/wiki/Ontology_(information_science)) using Controlled Natural Language (CNL)

Any particular reason why I'm not using [Gellish](http://www.gellish.net/)

## Controlled Natural Language (CNL)

I'm interested in the use of[Controlled Natural Language (CNL)](Controlled Natural Language) approaches to business/enterprise domains. The ultimate aim is to produce an [Ontology or (knowledge graph)](https://en.wikipedia.org/wiki/Ontology_(information_science)) that describes the [domain of discourse](https://en.wikipedia.org/wiki/Domain_of_discourse) within a business. This ontology can be used to support a range of activities including but not limitied to:

* Requirement gathering
* Change management
* Data quality
* [Domain Driven Design](https://en.wikipedia.org/wiki/Domain-driven_design)

CNL uses a controlled grammar to express knowledge. The CNL style employed has a number of benefits:

1. It is easy to use
1. It is human readable
    * It is easy to understand by the lay-person (domain expert)
1. It is machine readable
    * It can be translated into first-order logic

The below is an example of CNL expressed in ACE.

```CNL
All men are mortal.
John is a man.
What is mortal?

```

This Socratic sentence is easy to read and understand (whilst the question *What is mortal?* seems clumsy, it is still understandable). It's easy for us to provide the answer to the question:

> John is mortal. 

This is an example of [inference](https://en.wikipedia.org/wiki/Inference). The benefit comes when a computer can come to the same inference. This can be visualized in the [RACE (reasoning engine) web client](http://attempto.ifi.uzh.ch/race/) as demonstrated in the file AutomatedReasoningUsingRACE_whoIsMortal.mp4 in the video folder (put a link onto youtube).

Further benefits come when moving from inferencing over a small number of facts to inferencing over hundreds, thousands or millions of facts. 

We will use CNL to express short facts about the activities and functions of the business/enterprise. The major benefit for RoS is that these statements can be easily understood by domain experts and challenged. The things I'm looking for is moments where someone says....

> 'Hmm, well yes: that's mainly true. About 90% of the time that happens, but sometimes we need to do this.'

This means that the transcription of knowledge becomes transparent and we can get an unambiguous understanding of enterprise activities at different granularities. 

I believe this is specifically important in the articulation of a *Ubiquitous Language* within Domain Driven Design. Ubiquitous Language is defined as followes by Wikipedia:

> A language structured around the domain model and used by all team members to connect all the activities of the team with the software.
