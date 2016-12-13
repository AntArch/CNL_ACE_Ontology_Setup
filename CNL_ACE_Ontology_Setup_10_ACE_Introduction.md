# Attempto Controlled English (ACE) Overview

Attempto Controlled English (ACE) is part of the [Attempto Project](http://attempto.ifi.uzh.ch/site/). Attempto Controlled English (ACE) is a controlled natural language, i.e. a rich subset of standard English designed to serve as knowledge representation language. ACE allows users to express texts precisely, and in the terms of their respective application domain. As any language, ACE must be learned to be used competently, but this amounts to learning the differences between ACE and full English, formulated as a small set of ACE construction and interpretation rules. To simplify using ACE we have been developing the ACE Editor that helps users to construct correct ACE texts without having to learn it. Once written, ACE texts can be read and understood by anybody.

ACE and its tools are intended for professionals who want to use formal notations and formal methods, but may not be familiar with them. Thus the Attempto system has been designed in a way that allows users to work solely on the level of ACE without having to take recourse to its internal logic representation.

ACE appears perfectly natural, but — being a controlled subset of English — is in fact a formal language. ACE texts are computer-processable and can be unambiguously translated into discourse representation structures, a syntactic variant of first-order logic. Discourse representation structures derived from ACE texts have been translated into various other languages, for instance into FOL, FLUX, RuleML, R2ML, TPTP, and a rule format to be used for Courteous Logic Programs and for stable model semantics. Using discourse representation structures as inter-lingua we have developed a bidirectional translation of ACE into and from OWL 2 and a translation into SWRL.

## Tools used

A number of [tools have been developed for ACE](http://attempto.ifi.uzh.ch/site/tools/). We will use a subset of these:

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


