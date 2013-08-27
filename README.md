Addi
====

This repository is the home for the Async Data Discovery and Interchange (ADDI) specifications.

License
---------

<a rel="license" href="http://creativecommons.org/licenses/by-nd/3.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-nd/3.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">Async Data Discovery and Interchange (ADDI)</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nd/3.0/deed.en_US">Creative Commons Attribution-NoDerivs 3.0 Unported License</a>.

A Short Description of ADDI
---------------------------

ADDI is a set of specifications optimized for exchanging and discovering structured semantically-rich data in a secure distributed mesh of information where no one server has control, using a model suitable for distributed computing.

The specifications consist of the following documents:
* ADDI Basic Concepts
* ADDI Link Contracts
* ADDI Discovery and Resolution
* ADDI Data Model
* ADDI Resource Identifiers
* ADDI Semantics
* ADDI Use Cases (one document per use case)

More information will be in [An Introduction to ADDI](./topics/AnIntroductionToADDI.md), originally posted at [Nodal.info](http://www.nodal.info/2013/02/announcing-addi.html).

Status
-------

ADDI is on target for a v0.9 release later in 2013.  There are a lot of offline notes that are now being put into specification documents via separate reusable topics in the topics/ directory of this repository.  Each topic is authored in Markdown with extra comments to enable a Markdown -> DITA -> PDF and HTML chain.
 
Contributing
------------

You can contribute in any one of the following ways:
* Directly working on the document by forking the Github repo [https://github.com/BillBarnhill/ADDI](https://github.com/BillBarnhill/ADDI) and issuing a pull request, once we have a Contributor License Agreement from you (CLA), a form which will be available soon
* Participate on the Github ADDI Wiki [https://github.com/BillBarnhill/ADDI/wiki](https://github.com/BillBarnhill/ADDI/wiki)
* Submit an issue on Github [https://github.com/BillBarnhill/ADDI/issues](https://github.com/BillBarnhill/ADDI/issues)
* Participate in discussions on [the ADDI Loomio group](https://www.loomio.org/groups/1880) 

All feedback is welcome, and will be credited, but please be aware that this project is a personal dream of mine and as such I will have final say in the result.  I will always explain any decision though and will always be open to being convinced to change my mind.


Key Differentiating Features of ADDI 
-------------------------------------

* ADDI Link Contracts
  * [authoriZation Based Access Control](http://www.hpl.hp.com/techreports/2009/HPL-2009-30.pdf) (ZBAC)
  * Optional information sharing [obligations](http://openseminar.org/se/modules/232/index/screen.do)
  * Rich policy expression language in ADDI, so policy is data, and operations on policies can be controlled in the same way
  * Revocation of authorization by revoking the link contract
  * Link Contract participants as an addressable group (if allowed by policy)
  * Support for REST services via data state change hooks within link contracts
* Built-in decentralized discovery and resolution using trust metrics
* Semantically rich data model based on collections of (asserter,subject,predicate,object) tuples organized into Conflict-free Replicated Data Type (CRDT) Sets, a variation on [C-Sets](http://ceur-ws.org/Vol-737/paper9.pdf) 
* Built in semantic reasoning using the [Closed World assumption](http://en.wikipedia.org/wiki/Closed_world_assumption) (also see [this article](http://www.betaversion.org/~stefano/linotype/news/91/) ) 
* ADDI designed to be as transport agnostic as possible

Note: ADDI Link Contracts are similar to XDI Link Contracts in concept, but differ greatly in many aspects as ADDI Link Contracts are geared for the different design goals of ADDI and reflect different design decisions than those taken by the OASIS XDI TC.

Differences between ADDI and HTTP
--------------------------------------

* ADDI incorporates discovery, HTTP does not
* ADDI Resource Identifiers (ARIs) are based on Extensible Resource Identifiers (XRIs), so they are semantically rich and can express more that the same size URI
* ARI resolution is decentralized and trust based, using a trust metric computed from peers, HTTP resolution is DNS based with no trust metric
* HTTP is connection-oriented, ADDI supports connection-oriented and connection-less
* ADDI has Link Contracts (a concept developed in the OASIS XDI Technical Committee) 
* HTTP content consists of headers followed by MIME content, ADDI content consists of a stream of ADDI context state changes

Differences between ADDI and XDI
---------------------------------
* ADDI design goals are similarly aligned, but not equivalent, to XDI design goals - ADDI focuses on simplicity/human readability, decentralization, mandatory security, distributed computing, and distributed social networks
* More on the differences between ADDI and XDI will be written in a separate document




