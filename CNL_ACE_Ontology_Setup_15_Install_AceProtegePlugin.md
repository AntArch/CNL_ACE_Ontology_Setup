# Install ACE Protege plugin

The ACE plugin is a fabulous tool, it integrates directly into [Protege](http://protege.stanford.edu) (the open source ontology editor), allowing one to generate CNL statements and import them directly into the ontology editor. One can then leverage the power of Protege to visualize and analyse the results. Even though protege 4.3 is a bit long in the tooth once an ontology has been created it can be opened within newer versions with better visualization and analysis functions. 

Unfortunately development of the Protege Ace Viewer has stalled and the only current version is available for protege version 4.3. However, it's not quite as simple as downloading and installing the plugin - time has moved on and things get broken. But all is not over. 

* [Download and install Protege 4.3 for your preferred platform](http://protege.stanford.edu/download/protege/4.3/installanywhere/Web_Installers/)
* In the folder */bin/* where you installed protege
	* rename *felix.jar* to *felixOLD.jar*
* from the *ProtegeJars* folders in this GitHub repository:
	* copy *felix.jar* to the */bin/* where you installed protege
	* copy *ch.uzh.ifi.attempto.aceview.ui.view.jar* to the */plugins/* where you installed protege
	
In the *video* folder there is a video called *InstallProtegeWithACEView.webm* which describes this process.

Further introductory videos for protege include:

* Protege_AcePlugin_harderQuestions.webm
* ProtegePlugin_SimpleReasoningDemonstration.webm
