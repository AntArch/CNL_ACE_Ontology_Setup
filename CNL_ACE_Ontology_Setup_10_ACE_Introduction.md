# Attempto Controlled English (ACE) Overview

Attempto Controlled English (ACE) is part of the [Attempto Project](http://attempto.ifi.uzh.ch/site/). Attempto Controlled English (ACE) is a controlled natural language, i.e. a rich subset of standard English designed to serve as knowledge representation language. ACE allows users to express texts precisely, and in the terms of their respective application domain. As any language, ACE must be learned to be used competently, but this amounts to learning the differences between ACE and full English, formulated as a small set of ACE construction and interpretation rules. To simplify using ACE we have been developing the ACE Editor that helps users to construct correct ACE texts without having to learn it. Once written, ACE texts can be read and understood by anybody.

ACE and its tools are intended for professionals who want to use formal notations and formal methods, but may not be familiar with them. Thus the Attempto system has been designed in a way that allows users to work solely on the level of ACE without having to take recourse to its internal logic representation.

ACE appears perfectly natural, but — being a controlled subset of English — is in fact a formal language. ACE texts are computer-processable and can be unambiguously translated into discourse representation structures, a syntactic variant of first-order logic. Discourse representation structures derived from ACE texts have been translated into various other languages, for instance into FOL, FLUX, RuleML, R2ML, TPTP, and a rule format to be used for Courteous Logic Programs and for stable model semantics. Using discourse representation structures as inter-lingua we have developed a bidirectional translation of ACE into and from OWL 2 and a translation into SWRL.

## Tools used

A number of [tools have been developed for ACE](http://attempto.ifi.uzh.ch/site/tools/) (note there is a separate page from [tools and resources](http://attempto.ifi.uzh.ch/site/resources/). We will use a subset of these:

* APE (ACE parser)
	* A parser that provides:
		* shows how each sentence has been split into linguistic and semantic primitives.
	* Services
		* [interactive Web client](http://attempto.ifi.uzh.ch/ape/)
		* [command line web service](http://attempto.ifi.uzh.ch/site/docs/ape_webservice.html)
	* Support
		* [Lexicon specification](http://attempto.ifi.uzh.ch/site/docs/ace_lexicon.html)
		* [interactive Web client help](http://attempto.ifi.uzh.ch/site/docs/ape_webclient_help.html)
* RACE (ACE reasoner)
	* The ACE reasoner RACE allows users to do deduction on ACE texts, for example consistency checks and query answering.
	* Services
		* [RACE interactive web client](http://attempto.ifi.uzh.ch/race/)
* AceRules
	* A service that materialises inferences based on rules
	* Services
		* [ARE rules interface](http://attempto.ifi.uzh.ch/acerules/)
			* doesn't seem to work
		* [ARE rules technical interface (for developers)](http://attempto.ifi.uzh.ch/acerules_ti/)
	* Support
		* [Documentation for AceRules Webservice](http://attempto.ifi.uzh.ch/site/docs/acerules_webservice.html)
* AceWiki
	* AceWiki is a semantic wiki using ACE. Unlike most other semantic wikis, the semantics are contained directly in the article texts and not in some form of annotations.
	* [AceWiki project site](http://attempto.ifi.uzh.ch/acewiki/)
	* There is a docker instances
* OWL verbalizer
	* OWL verbalizer converts OWL ontologies (expressed in XML Serialization) into ACE.
		* This conversion is designed to be reversible, i.e. one can convert the ACE representation back into OWL so that no loss in meaning occurs. 
	* [OWL verbalizer project page](https://github.com/Kaljurand/owl-verbalizer)
* ACE editor
	* The ACE Editor demonstrates how editing of ACE texts can be done in a convenient way. The ACE Editor is not a finished tool but rather a general basis to create domain-specific tools on top of it.
	* Services
		* [ACE editor](http://attempto.ifi.uzh.ch/aceeditor/)

	
## Copying stuff to and from a docker instances

### copying **from** docker

docker cp <docker instance>:<source folder> <local target folder>

Examples:

To the current folder - 

> docker cp serene_boyd:/AceWiki/data .

To a specific folder
> docker cp serene_boyd:/AceWiki/data /home/beckant/delme/Grr

### copying **to** docker	

# More docker

docker pull tkuhn/acewiki
docker start tkuhn/acewiki
docker build tkuhn/acewiki
docker ps -a
docker images

## getting a bash shell into docker

docker start <docker instance>
docker exec -i -t <docker instance> /bin/bash

docker start serene_boyd
docker exec -i -t serene_boyd /bin/bash



Some text to use in these services:

```cnl
Short_register is a register.
Short_register contains Shorts.
Register_of_Jumpers is a register.
Register_of_Shirts is a register.
Lapel_register is a register.
Cap_register is a register.
Registers_of_Clothing manages Short_register.
Registers_of_Clothing manages Register_of_Jumpers.
Registers_of_Clothing manages Register_of_Shirts.
Registers_of_Clothing manages Lapel_register.
Registers_of_Clothing manages Cap_register.
Short_Registration_Service applies to Short_register.
Lapel_Registration_Service applies to Lapel_register.
Starching applies to Lapel_Registration_Service.
Purchase_Notice applies to Short_Registration_Service.
Purchase_Notice applies to Lapel_Registration_Service.
```

```cnl
short_register is a register.
short_register contains shorts.
register_of_jumpers is a register.
register_of_shirts is a register.
lapel_register is a register.
cap_register is a register.
registers_of_clothing manages short_register.
registers_of_clothing manages register_of_jumpers.
registers_of_clothing manages register_of_shirts.
registers_of_clothing manages lapel_register.
registers_of_clothing manages cap_register.
short_registration_service applies to short_register.
lapel_registration_service applies to lapel_register.
starching applies to lapel_registration_service.
purchase_notice applies to short_registration_service.
purchase_notice applies to lapel_registration_service.
```

```cnl
short-register is a register.
short-register contains shorts.
register-of-jumpers is a register.
register-of-shirts is a register.
lapel-register is a register.
cap-register is a register.
registers-of-clothing manages short-register.
registers-of-clothing manages register-of-jumpers.
registers-of-clothing manages register-of-shirts.
registers-of-clothing manages lapel-register.
registers-of-clothing manages cap-register.
short-registration-service applies to short-register.
lapel-registration-service applies to lapel-register.
starching applies to lapel-registration-service.
purchase-notice applies to short-registration-service.
purchase-notice applies to lapel-registration-service.
```
