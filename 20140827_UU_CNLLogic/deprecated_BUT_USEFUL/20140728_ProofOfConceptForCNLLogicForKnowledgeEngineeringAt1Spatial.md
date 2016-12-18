---
title:  '*Proof of Concept*
\newline
Controlled Natural Language Logic For Knowledge Engineering At 1Spatial'
author: Anthony Beck
tags: Ontology, Business Process, 1Spatial, Knowledge Engineering, CNL
bibliography: ARB_Library.bib
csl: harvard.csl
abstract: |
  
  1Spatial is in the business of data quality. The software portfolio is aimed at the collection and collation of spatial data and the auditing, integration and enhancement of corporate spatial data assets. The spatial functionality can be deprecated to provide generic data quality enhancements. Much of the consulting work involves building longer-term synergistic relationships with large corporations who recognise the benefits of good quality provenanced data on operational processes. The premise for consultant activities is as follows:
  
  >Good quality data with a well understood scope leads to better decisions. 

  During consultation we need to rapidly determine a number of things:

  * the actual nature of the data (a data profiling exercise)
  * the expected nature of the data (an 'as-design' data modelling exercise)
  * the business problems which the data is expected to help solve (a business modelling exercise)
  * the business operational processes (an 'as-built' data modelling exercise)^[Not completely happy with this]

  The ability to express rules and logic in syntactically simple phrases is becoming increasingly important to how we develop an understanding and effectively communicating our clients business needs (expecially in helping to distinguish between their pre-conceived and actual need). To facilitate this process 1Spatial uses [*RuleSpeak*](http://www.rulespeak.com/en/) to both capture and communicate business rules. RuleSpeak is an example of a Controlled Natural Language (CNL). The point is to build an understanding of how the business systems are expected to function (the 'as-design' model) and compare this to how they actually function (the 'as-built' model) mediated by the problems the business systems are expected to solve (the business process model). Much of this information is undocumented and needs extracting from domain experts. Domain experts are not knowledge engineers or logicians. CNL helps extract this information in a manner which the domain experts can understand and provide feedback on. Hence, the abstracted model is a closer reflection to reality. 
  
  Whilst the RuleSpeak CNL reduces or removes ambiguity it is only understandable by a human reader^[I don't know of a RuleSpeak Natural Language Processing (NLP) parser]. The Knowledge Engineering community have developed other CNLs which can be used to create Formal Ontologies.

  Ontologies are a way to capture and share people’s knowledge about the world in a way that is processable by computer systems. Ontologies have the potential to serve as a bridge between the human conceptual understanding of the world and the data produced, processed and stored in computer systems. CNL can be used to develop ontologies then we can use to enhance our approaches and improve our services. 
  
  This document describes a proof of concept implementation of the ACE/APE CNL which can be used to derive an OWL formal ontology which in turn can be used for automated reasoning. The data depolyed is based upon a real case study from United Utilities based on the Open Water policy initiative. Capture of data in this manner will allow 1Spatial to build up a formal knowledge base which could have a major impact on company operations.
  
  This proof-of-concept has not been produced on 1Spatial company time. 
  \newpage
...

\newpage


Distribution list:

* Mike Sanderson
* Matt Beare
* Alan Howie
* Bob Chell
* Stephen Stanley 


A version of this document needs sending to UU

* John Daniels
* Lee Mooney (lee.mooney@uuplc.co.uk)

\newpage


#Rules, Ontologies and the 1Spatial consultancy model^[Speak to Alan about this]

The ability to express rules and logic in syntactically simple phrases is becoming increasingly important to how we develop an understanding of clients business needs and then effectively communicating this understanding to our clients. This is particularly important when identifying the difference between a client's pre-conceived need and their actual need (as reflected in the data and the surrounding business processes). To facilitate this 1Spatial use [*RuleSpeak*](http://www.rulespeak.com/en/) to both capture and communicate business rules. RuleSpeak is an example of a Controlled Natural Language (CNL). Whilst Rulespeak reduces or removes ambiguity it is only understandable by a human reader^[I don't know of a RuleSpeak Natural Language Processing (NLP) parser]. There are other CNLs which have been developed in the Knowledge Engineering community which focus on developing Formal Ontologies. This extends the utility of the rules by ensuring they are human *and computer* readable.

Ontologies have been proposed and studied in the last couple of decades as a way to capture and share people’s knowledge about the world in a way that is 'computer readable'. Ontologies have the potential to serve as a bridge between the human conceptual understanding of the world and the abstracted view of the world stored in computer systems. 

One of the main reasons for the lack of widespread adoption of ontologies is the steep learning curve for authoring them: most people find it too difficult to learn the syntax and formal semantics of ontology languages. If CNL can be used to develop ontologies then we can produce a more formal and rigorous method of modelling data, conceptual and business processes and sharing these models in meaningful ways with our business partners. For 1Spatial this has the added benefit of *accruing a knowledge base*. 

From a consultancy perspective 1Spatial is employed because the added business value to the client is greater than the cost of adding the value^[this cost is not always calculated financially: improving business value may be mandated by changes in policy terms with metrics that are not calculated financially but where failure to achieve such metrics does incur a financial penalty]. **Quality and knowledge is our business**.

During consultation we need to rapidly determine a number of things:

* the actual nature of the data (a data profiling exercise)
* the expected nature of the data (an 'as-design' conceptual modelling exercise)
* the business problems which the data is expected to help solve (a business requirements exercise)
* the business operational processes (an 'as-built' business modelling exercise)^[Not completely happy with this]

1Spatial has generic skills in data and spatial data quality enhancement but also has expert knowledge in different operational sectors (National Mapping Agencies, Utilities, Defense, Transport etc.). However, we are poor at re-using this knowledge. **Being able to effectively re-use our *knowledge base* provides 1Spatial with a significant competitive advantage.** 1Spatial can capitilise on the knowledge gained from each project more effectively. When working in in different organisations which refelct our domains of expertise^[each with different but complementary views over the same domain] there already exists a domain rich model which can be re-used in different business environments (i.e. we already know how *utility A* models water assets.... can this be used to help solve problems for *utility B*?). This knowledge should can also be used to identify new market opportunities: for example, the impacts of a new policy initiative (or policy change) can be modelled and inform products and services which can be pitched across the different sectors in a timely manner^[This is precisely the case for the clean and waste water sector of the utility market where the *Open Water* initiative represents a significant business opportunity for 1Spatial]. 

The ability to rapidly generate formal models and build these into a corporate knowledge base represents a significant opportunity for 1Spatial to transform and improve how it operates^[Alan: would appreciate your perspective on this]. This document outlines a proof of concept approach for generating such models.

#Controlled Natural Language systems for Ontology engineering

Ontology development requires at least two types of people:

* A knowledge engineer - who can structure the underlying logic that supports the knowledge model
* A domain expert - who has in depth understanding and experience of the phenomena to be modelled

The mathematical nature of description logic has meant that domain experts find them hard to understand. This forms a significant impediment to the creation and adoption of ontologies. Ontology focussed Controlled Natural Language systems constrain language syntax and allow statements to be translated into the Web Ontology Language (OWL) with the aim of achieving both comprehension by domain experts and computational preciseness. 

The fundamental principles underlying the use of CNLs for Ontology engineering are (after @denaux_intuitive_2013):

* To allow the domain expert, with the aid of a knowledge engineer and tool support, to express their knowledge as easily and simply as possible and in as much detail as necessary.
* To have a well defined grammar and be sufficiently formal to enable those aspects that can be expressed as OWL to be systematically translatable.
* To be comprehensible by domain experts with little or no knowledge of OWL.
* To be independent of any specific domain.

These principles can be achieved - at least in part. One such example is the use of the Rabbit CNL developed by Ordnance Survey (@hart_rabbit:_2008):

>The original intention was for Rabbit to enable domain experts alone to author ontologies. However, practice showed that whilst domain experts could build ontologies, these ontologies often contained many modelling errors not related to the language but the modelling processes. None-the-less Rabbit still enables the domain expert to take the lead and to author ontologies with guidance in modelling techniques from a knowledge engineer. Rabbit also enables other domain experts to verify the ontology.

CNLs should contain a number of language element. Those used to 

* express axioms
* introduce (or declare) concepts and relationships
* ADD MORE

##Candidate systems

Two candidate systems were considered:

* ROO and Rabbit [@denaux_intuitive_2013, @hart_rabbit:_2008]
* APE and ACE [@_attempto_2014]

>We see Rabbit as complementary to OWL, extending its reach to those who need to author and understand domain ontologies but for whom descriptions logics are difficult to comprehend even when expressed in more user-friendly forms such as the Manchester Syntax.

ROO is a .....

Rabbit is a 



###APE and ACE 


#Proof of concept problem - The impact of Open Water and United Utilities

United Utilities (UU) provides both *water* and *wastewater services*. The location of the *termination point* of a United Utilities *wholesale service asset* to a customer is called a *service point*. These service points may be for water supply, sewerage services, metering, trade effluent and any other service within the wholesale service catalogue. A service point is a sub-set of the UU wholesale assets which is uniquely billable and has a geographical location. This locational geography needs to adequately represent billing and operational activities. 

![Service Point connectivity at United Utilities ](/home/arb/Seafile/Working/1Spatial_Projects/Jobs/20140701_UU/Illustrations/ServiceConnectivity.png)

The Address Management System (AMS) fulfills parts of this need. AMS is a bespoke data repository holding *Service Point Addresses* for water, wastewater and electricity (now deprecated) domains. AMS is not an address gazetteer. 

![The UU Address Management System](/home/arb/Seafile/Working/1Spatial_Projects/Jobs/20140701_UU/Illustrations/AMS_InDetail.png)

AMS records are related to a *service point*:

* In most cases these service points are at an addressable property (or a *standard address*) such as a house or office. These have an *address_type* of *postal* (PO).
	* There are also some legacy records that refer to postal addresses outside the UU operational area. These have an *address_type* of *foreign* (FO).
* Some AMS records are related to potential future service points which will be constructed. These represent *plot addresses*. These have an *address_type* of *plot* (PL).
* The AMS record might refer to a service point feeding a cattle trough or a railway signalling box. These represent *non-standard addresses*. These have an *address_type* of *locational* (LO).

At present UU only provides *wholesale* services. When the [Open Water initiative](http://www.open-water.org.uk/) is enacted UU will be split into a *wholesale* and *retail* business. The wholesale part of UU will sell services to a small number of elegible third parties (including the retail part of UU) who will act as retail agents. These elegible retail agents will sell services to individual consumers. The wholesale business will provide transparent systems to all eligible retail businesses. Key to this will be the interoperable exchange of *service point* information. This implies that after Open Water has been enacted there will be both *Retail Service Points* and *Wholesale Service Points*. UU has recognised the important and potentially disruptive impact of Open Water. This recognition underpins the Service Point Address (SPA) project:

>In the coming competitive environment, the importance of the service point address will increase.  On 2nd January 2014, the OpenWater Group published documentation on how it sees the competitive market operating.  A fundamental requirement for market operation is “for registration and switching, a centrally held record of premises, service points, and associated meters and market participants”. The ability of suppliers to interact and automatically match to this data will be critical in running an efficient business.

>The current addressing system suffers from poor integration with existing systems including Alto and IWM, poor data quality and is based on an end of life, custom application. 

>Service point address (SPA) will provide a single version of the truth for property addresses and service point locations within the strategic UUGIS (LAM) application and integrate to other key enterprise applications (IWM, Alto).  Our critical success will be ensuring that when dealing with a property which receives a UU service, all of our teams are presented with consistent, accurate information about the property address and location.

Other utility companies in the water domain will be responding to this policy initiative. 


#Bibliography
