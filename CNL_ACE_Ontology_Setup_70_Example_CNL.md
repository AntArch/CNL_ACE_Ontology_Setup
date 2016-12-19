### Classes and properties

A series of simple statements that define classes and properties. The validity of these statements can be easily tested by domain experts in the business. It is important to ensure that edge cases are detected^[for example - whilst the statement holds for most things it doesn't work when X or Y]

Every lateralPoint is an asset .

Every lateralPoint hasGeometry node .

Every lateralLine is an asset .

Every lateralLine hasGeometry line .

Every main is a lateralLine .

Every main is a wholesaleAsset .

Every commsPipe is a lateralLine .

Every commsPipe is a wholesaleAsset .

Every privatePipe is a lateralLine .

Every privatePipe is a retailAsset .

Every ferrule is a lateralPoint .

Every meter is a lateralPoint .

Every stopTap is a lateralPoint .

Every meterAndStop is a lateralPoint .

Every serviceStart is a lateralPoint .

Every serviceStart is a ferrule .

Every serviceStart is a wholesaleAsset .

Every distributionServicePoint is a serviceStart .

Every servicePoint is a lateralPoint .

Every servicePoint is a wholesaleAsset and is a retailAsset.

Every wholesaleServicePoint is a servicePoint .

Every serviceEnd is a lateralPoint .

Every serviceEnd is a retailAsset .

### General constraints

Constraints have been given to the classes (and by extension their instances) which are defined above.

Every serviceStart is physicallyConnected to 1 main and 1 commsPipe .

Every servicePoint is a stopTap or is a meter or is a meterAndStop .

Every servicePoint is physicallyConnected to 1 main and at least 1 commsPipe .

Every serviceEnd is physicallyConnected to 1 commsPipe .

### Transitivity rules

Some transitivity rules are detailed below. That explain that if A is *physicallyConnected* to B and B *physicallyConnected* to C then A is part of the same network as C. There is also an inverse statement so that connections can be identified irrespective of direction.

If something X follows something that follows something Y then X follows Y.

If something X physicallyConnected something that physicallyConnected something Y then X networkConnected Y.

If something X physicallyConnected something Y then something Y physicallyConnected X.

If something X physicallyConnected something Y then something X networkConnected Y.

If something X networkConnected something Y then something Y networkConnected X.

If something X is taller than something Y and Y is taller than something Z then X is taller than Z.

If something X is upstream of something Y and Y is upstream of something Z then X is upstream of Z.

If something X is upstream of something Y then Y is downstream of X.


If something X is physicallyConnected something Y and Y is physicallyConnected something Z then X is networkConnected Z.

### Individuals

Some individuals have been created. These can be used to test the validity of statements about concepts and to test connectivity. A *physicallyConnected* network has been generated.

ID_12345 is a ferrule .

ID_12345 is a serviceStart .

ID_12345 physicallyConnected ID_45678 .

ID_45678 physicallyConnected ID_99999 .

ID_99999 physicallyConnected ID_99998 .

Every retailServicePoint is a serviceEnd .

### Questions for the reasoner to answer

Some questions have been stated for the reasoner to answer:

What is a ferrule ?

What is ID_12345 ?

What is an asset ?

What is a wholesaleAsset ?

Is ID_99998 networkConnected ID_12345 ?

### Entailment (what does this imply)

To support this section a 4 minute video has been created that shows how the ACE/APE CNL statements can be loaded into the [Protege ontology editor](http://protege.stanford.edu/). There are two versions of this video (if there are issues in accessing these videos then they can be supplied in alternative ways):

* [Original webm](ftp://79.77.41.237/FTPBeck/1SpatialTemp/CNL_Ontology/OverviewOfProtegeAndACEAPE_CNL.webm)
* [Converted wmv (for windows users who do not have the appropriate codecs) ](ftp://79.77.41.237/FTPBeck/1SpatialTemp/CNL_Ontology/OverviewOfProtegeAndACEAPE_CNL.wmv)

Relationships between the statements can be quickly visualised in Protege as shown in Figure \ref{AssertedRelationships}. This facility alone is an enhancement to that offered by RuleSpeak.

![A visualization of the CNL concepts in protege\label{AssertedRelationships}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/AssertedRelationships.png)

As explained in the videos a number of different visualizations, views and facts can be seen using the built in tools in Protege. In addition we have used ACE/APE to ask a number of questions of the ontology as detailed in the figures below:

![What is a Ferrule?\label{WhatIsAFerrule}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/WhatIsAFerrule.png)

![What is an Asset?\label{WhatIsAnAsset}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/WhatIsAnAsset.png)

![What is a Wholesale Asset?\label{WhatIsAWholeSaleAsset}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/WhatIsAWholeSaleAsset.png)

![What is ID_12345?\label{WhatIsID_12345}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/WhatIsID_12345.png)

## The CNL developed for Open Water based on the [Systems Architecture and Data Model](http://www.open-water.org.uk/media/1047/systems-architecture-and-data-model.pdf) document

Open Water have produced a number of consultation documents. This architectural overview has been taken from @open_water_systems_2014 and @open_water_systems_2014-1.

This was *partially* modelled to create the following CNL and is therefore not fully articulated.

### Classes

#### Nature of the operators

Every wholesaleOperator is a marketParticipant .

Every retailOperator is a marketParticipant .

Every marketOperator is a marketParticipant .

marketOperator is at most one thing .

Every wholesaleOperator is a waSC or is a wOC or is a nAV .

Every retailOperator is a waSC or is a wOC or is a nAV .

#### IT requirements

Every registrationDatabase is a database .

Every registrationDatabase holdsInformation sites .

Every registrationDatabase holdsInformation parties .

Every registrationDatabase provides registrationServices .

Every registrationDatabase provides switchingServices .

Every switchingService is a service .

Every registrationService is a service .

Every financialDatabase is a database .

Every financialDatabase holdsInformation meterReadings .

Every financialDatabase provides financialServices .

Every financialDatabase provides settlementServices .

Every settlementService is a financialService .

Every settlementService requires a calculationSystem and a meterReading and a wholesaleOperator and a retailOperator .

Every financialService is a service .

### Properties

Every servicePoint hasCustomerUPRN a UPRN.

Every servicePoint hasCustomerUPRN at most one thing .

Every servicePoint hasRetailer a retailOperator

Every servicePoint hasRetailer exactly one thing .

Every servicePoint hasWholesaler a wholesaleOperator.

Every servicePoint hasWholesaler exactly one thing .

Every meter hasServicePoint a servicePoint.

Every meter hasServicePoint at least one thing .

Every meter hasMeterType a meterType.

Every meter hasMeterType exactly one thing .

Every meter hasSerialNumber a serialNumber .

Every meter hasSerialNumber exactly one thing .

Every meter hasInstallDate a installDate .

Every meter hasInstallDate exactly one thing .

Every meter hasUseStatus a useStatus .

Every meter hasUseStatus exactly one thing .

Every meter hasMeterReading a meterReading .

Every meter hasMeterReading at least one thing .

### Elements not yet modelled

* a conceptual model for registration data;
* a conceptual model for service request data;
* a conceptual data model for consumption and financial settlement data;
* and indicative event and data volumes.


### Individuals

UU is a waSC .

UU is a wholesaleOperator .

UU is a wholesaleOperator .

UU is not a marketOperator .

### Entailment

Figure \ref{AssertedRelationships2} is a visualization of the [Systems Architecture and Data Model](http://www.open-water.org.uk/media/1047/systems-architecture-and-data-model.pdf) concepts described in CNL and turned into an OWL ontology.

![A visualization of the Systems Architecture and Data Model concepts in CNL\label{AssertedRelationships2}](/home/arb/ownCloud/documents/CommonMarkDocs/20140827_UU_CNLLogic/Images/AssertedRelationships2.png)

# Summary 

* Rapidly understand systems
* Rapidly visualize relationships and frameworks
* Be able to undertake quality improvement from Top down (*conceptual*) and bottom up (*how the data has been physically modelled*)
* Transfer knowledge and re-use within new environments
* Communicate knowledge more effectively within teams and to third parties
* Store knowledge so it can be re-used in downstream projects and products
* Sell services based upon the knowledge model

# From Matts Powerpoint

## What is a supplyPoint

Every wholesaleOperator hasConcept supplyPoint.

A registeredSupplyPoint is a supplyPoint.

A registeredSupplyPoint providesService Water or providesService Sewer.

mrSPID is same as registeredSupplyPoint .

mrSPID has minCardinality 1.

mrSPID has maxCardinality 2.

Every supplyPoint hasConcept supplyPoint.

supplyPoint hasLabel 'Supply Point is a conceptual aggregation of services for any identified premise (Domestic or Non-Domestic)'.

Every mrSPID is either a


## Concepts

Service Point - A point on the Wholesale network from which services are supplied. SPA will identify Service points and allocate X,Y co-ordinates and a standard address

Standard Address

WholesaleNetwork

Consumption Point - A property, building or feature at which services are consumed by a customer

Property

Building

Feature

Service

Customer

Consume

Meter Address - Where a service is measured, SPA will identify the meter associated with each service associated with each service association in effect providing x,y co-ordinates and standard addresses for each market meter.

Meter

Market meter

Relationships between services, service associations, meters. What is the cardinality







