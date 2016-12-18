\newpage

#The Rule Base

A Wholesale Service Point is a conceptual thing
A Wholesale Service Point is the same as a Service Point (Really?)
A Wholesale Service Point has a location by association to a physical thing
A Wholesale Service Point has a conceptual relationship to one and only one Lateral Point Asset which has a sub-type 'Stop tap' or Meter or 'Meter and Stop' (Requires confirmation)
	If the related Lateral Point Asset does not exist associate to Service Start in FCS
#A Wholesale Service Point is uniquely billable (no it isn't becuase the Retail Service Point owners will be able to decide who provides the service)
A Wholesale Service Point can be used by one or more Retail Service Points (which entails there can be one or more billable retail user per Wholesale Service Point)
A Wholesale Service Point represents the start of a Wholesale Business Process for Waste Water
A Wholesale Service Point represents the end of a Wholesale Business Process for Clean Water
A Wholesale Service Point has a physical connection to at least one Retail Service Point
A Wholesale Service Point has to exist for every Retail Service Point (this entails there is a Wholesale Service Point for every billable asset)

A single Lateral Point Asset can have a conceptual relationship with both a Wholesale Service Point AND a Retail Service Point 

A Retail Service Point is a conceptual thing
A Retail Service Point is the same as a Consumption Point when the Domain is Clean Water
A Retail Service Point is the same as a Contribution Point when the Domain is Waste Water
A Retail Service Point has a location by association toService a physical thing
A Retail Service Point has a conceptual relationship to one and only one Lateral Point Asset which has a sub-type 'Service End' AND Domain 'Clean Water' or ???? (Requires confirmation)
	If the related Lateral Point Asset does not exist associate to Billable Address
A Consumption Point is the end of a Retail Business Process
A Contribution Point is the start of a Retail Business Process
	A Retail Service Point represents the start or end of a Retail Business Process (by entailment)
A Retail Service Point has a location by association to a physical thing
A Retail Service Point is uniquely billable
A Retail Service Point has a physical connection to a Wholesale Service Point

A Service Start is a physical thing
A Service Start has a location
A Service Start is a Lateral Point Asset which has a sub-type 'Service Start' in UUGIS (Requires confirmation)
A Service Start has a physical connection to Lateral Point Asset which has a conceptual relationship with a Wholesale Service Point

A Service End is a physical thing
A Service End has a location
A Service End is a Lateral Point Asset which has a sub-type 'Service End' in UUGIS (Requires confirmation)
A Service End is part of the 

A Lateral Point Asset is a physical thing
A Lateral Point Asset has a location
A Lateral Point Asset is in UUGIS (Requires confirmation)
A Lateral Point Asset with sub
A single Lateral Point Asset can have a conceptual relationship with both a Wholesale Service Point AND a Retail Service Point 

For every Retail Service Point there is a Service to a Main

A Retail Service Point must have a 
Some Retail Service Points are associated with a building that has a UPRN
Some Retail Service Points are associated with a building that does not have a UPRN
Some Retail Service Points are NOT associated with a building
All Retail Service Points all billable entitiesA conumption 
A Retail Service Point is a thing

FCS is providing Service assets and Retail Service Points where they dont exist
Some Retail Service Points are within or connected to a building with a UPRN
Other Retail Service Points  have an abstracted connection to a building with a UPRN

Some Wholesale Service Points have a physical connection to a building with a UPRN
Other Wholesale Service Points have an abstracted connection to a building with a UPRN

WIRS/SIRS addresses will not have a creation year > 2005

Junk AMS_IDS should be cross-referenced against ALTO prior to deletion (we should profile what intersects here - WIRS/SIRS shouldn't exist)
