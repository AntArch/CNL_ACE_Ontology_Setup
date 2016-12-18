\newpage

#Outstanding rule requirements

Need to add in transitivity - the question 'what is a wholesaleAsset' should pick up ferrule and the individual

#From UU view of Open Water

##ACE Rule Base

Every lateralPoint is an asset .

Every lateralPoint hasGeometry node .

Every lateralLine is an asset .

Every lateralLine hasGeometry line .

ID_12345 is a ferrule .

ID_12345 is a serviceStart .

ID_12345 physicallyConnected ID_45678 .

ID_45678 physicallyConnected ID_99999 .

ID_99999 physicallyConnected ID_99998 .

Is ID_99998 networkConnected ID_12345 ?

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

Every serviceStart is physicallyConnected to 1 main and 1 commsPipe .

Every serviceStart is a wholesaleAsset .

Every distributionServicePoint is a serviceStart .

Every servicePoint is a lateralPoint .

Every servicePoint is a stopTap or is a meter or is a meterAndStop .

Every servicePoint is physicallyConnected to 1 main and at least 1 commsPipe .

Every servicePoint is a wholesaleAsset and is a retailAsset.

Every wholesaleServicePoint is a servicePoint .

Every serviceEnd is a lateralPoint .

Every serviceEnd is physicallyConnected to 1 commsPipe .

Every serviceEnd is a retailAsset .

Every retailServicePoint is a serviceEnd .

What is a wholesaleAsset ?

What is a ferrule ?

What is ID_12345 ?

What is an asset ?

What is networkConnected ?

##ACE transitivity rules

If something X follows something that follows something Y then X follows Y.

If something X physicallyConnected something that physicallyConnected something Y then X networkConnected Y.

If something X physicallyConnected something Y then something Y physicallyConnected X.

If something X is taller than something Y and Y is taller than something Z then X is taller than Z.

If something X is physicallyConnected something Y and Y is physicallyConnected something Z then X is networkConnected Z.



