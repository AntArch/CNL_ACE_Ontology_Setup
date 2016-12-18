
# Market Reform CNL: The impact of Open Water

This document was written on 2014-08-27 and reflects the knowledge acquired prior to this point. It has not been updated since this time to reflect developments in SPA or FCS.


## United Utilities

United Utilities (UU) provides both *water* and *wastewater services*. The location of the *termination point* of a United Utilities *wholesale service asset* to a customer is called a *service point*. These service points may be for water supply, sewerage services, metering, trade effluent and any other service within the wholesale service catalogue. A service point is a sub-set of the UU wholesale assets which is uniquely billable and has a geographical location. This locational geography needs to adequately represent billing and operational activities.

The Address Management System (AMS) fulfills parts of this need. AMS is a bespoke data repository holding *Service Point Addresses* for water, wastewater and electricity (now deprecated) domains. AMS is not an address gazetteer. Figure \ref{AMSOverview} provides an overview of AMS.

![The UU Address Management System\label{AMSOverview}](/home/arb/Dropbox/Public/ImageBank/AMS_InDetail.png)

AMS records are related to a *service point*:

* In most cases these service points are at an addressable property (or a *standard address*) such as a house or office. These have an *address_type* of *postal* (PO).
	* There are also some legacy records that refer to postal addresses outside the UU operational area. These have an *address_type* of *foreign* (FO).
* Some AMS records are related to potential future service points which will be constructed. These represent *plot addresses*. These have an *address_type* of *plot* (PL).
* The AMS record might refer to a service point feeding a cattle trough or a railway signalling box. These represent *non-standard addresses*. These have an *address_type* of *locational* (LO).

## Open Water

At present UU only provides *wholesale* services. When the [Open Water initiative](http://www.open-water.org.uk/) is enacted UU will be split into a *wholesale* and *retail* business. The wholesale part of UU will sell services to a small number of elegible third parties (including the retail part of UU) who will act as retail agents. These elegible retail agents will sell services to individual consumers. The wholesale business will provide transparent systems to all eligible retail businesses. Key to this will be the interoperable exchange of *service point* information. This implies that after Open Water has been enacted there will be both *Retail Service Points* and *Wholesale Service Points*. UU has recognised the important and potentially disruptive impact of Open Water. This recognition underpins the Service Point Address (SPA) project:

>In the coming competitive environment, the importance of the service point address will increase.  On 2nd January 2014, the OpenWater Group published documentation on how it sees the competitive market operating.  A fundamental requirement for market operation is “for registration and switching, a centrally held record of premises, service points, and associated meters and market participants”. The ability of suppliers to interact and automatically match to this data will be critical in running an efficient business.

>The current addressing system suffers from poor integration with existing systems including Alto and IWM, poor data quality and is based on an end of life, custom application.

>Service point address (SPA) will provide a single version of the truth for property addresses and service point locations within the strategic UUGIS (LAM) application and integrate to other key enterprise applications (IWM, Alto).  Our critical success will be ensuring that when dealing with a property which receives a UU service, all of our teams are presented with consistent, accurate information about the property address and location.

The Open Water policy initiative will be very disruptive to the Water domain. Other utility companies in the water domain will be responding to this policy initiative.

## The CNL developed for Open Water based on UU views of its assets

On 17th July there was a meeting at UU as part of the SPA project which discussed the forthcoming *Open Water* initiative in significant detail. It became apparent that the impact of Open Water was unclear. This was not helped by semantic and conceptual issues. For example the terminology had multiple interpretations that could be construed differently depending upon the mental models employed. Based upon this experience it was determined that a better way of sharing this information was required^[this is an important point: the benefits described here are not primarily about the moelling and inferencing capabilities of an ontology but in providing a team with clear and unambiguous representations].

This meeting resulted in Figure \ref{ServicePointConnectivity}: a conceptual model that identifies the nature of Service Points and connectivity of the physical assets in relation to Open Water. These relationships have been encoded as CNL as detailed below

![Service Point connectivity at United Utilities\label{ServicePointConnectivity}](/home/arb/Dropbox/Public/ImageBank/ServiceConnectivity.png)

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







