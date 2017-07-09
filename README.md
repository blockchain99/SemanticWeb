### Ask not “How can we make the Web infrastructure smarter?” 
## But ask “What can the Web infrastructure provide to improve the consistency and availability of Web data?"

* ### A Connected Web Is a Smarter Web.
* “we need a Web infrastructure that lets us connect data to smart Web applications so that the whole Web experience is enhanced. The Web seems smarter because smart applications can get the data they need.

### When we speak of “semantics” of natural language, we often refer to something about what it means to understand the utterance—how to go from the structured letters or sounds in a language to some kind of meaning behind them.

* That is, given that symbols can refer to things in the world, how can we build models from those symbols that help us to capture, understand, and communicate what we know about relationships between those things?

* In the Semantic Web we refer to the things in the world as resources; a resource can be anything that someonemight want to talk about.
Followings are all examples of things someonemight talk about and that can be resources in the SemanticWeb.

> Subject X is "Harald" and Object(Literal) Y is "++49-331-5509-927", which is “the value of X,” and Predicate, P is “phone”
> Subject X is "Harald" and Object(Resource) Y is "http://harald.blogspot.com/", which is “the value of X,” and Predicate, P is “weblog”

![semantic web graph]({{http://www.patternics.com}}/SemanticWeb/image/rdf1.JPG)

### 1.  N-Triples Notation

• URIs/IRIs in angle brackets

• Literals in quotation marks

• Triple ends with a period

> <http://harald.sack.de/foaf.rdf#harald> <http://xmlns.com/foaf/0.1/phone> “+
> +49-331-5509-927“ .
> <http://harald.sack.de/foaf.rdf#harald> <http://xmlns.com/foaf/0.1/weblog>
> <http://harald.blogspot.com/> .

### 2. Turtle (Terse RDF Tripel Language) Notation
> @prefix foaf: <http://xmlns.com/foaf/0.1/> .
> @base <http://harald.sack.de/foaf.rdf>
> <#harald> foaf:phone “++49-331-5509-927“ .
> <#harald> foaf:weblog <http://harald.blogspot.com/> .

* Below "Turtle Notation with ;" has same result with above Trutle Notation : semicolon indicates that subsequent triples have the same subject

> @prefix foaf: <http://xmlns.com/foaf/0.1/> .
> @base <http://harald.sack.de/foaf.rdf>
> <#harald> foaf:phone “++49-331-5509-527“ ; foaf:weblog <http://semweb2014.blogspot.com/> .

![semantic web graph:rdf2]({{http://www.patternics.com}}/SemanticWeb/image/rdf2.JPG)

* comma indicates that subsequent triples have same subject and property (object list)
> @prefix foaf: <http://xmlns.com/foaf/0.1/> .
> <#harald> foaf:weblog <http://semweb2014.blogspot.com/> ,
> <http://semweb2013.blogspot.com/> ,
> <http://semweb2012.blogspot.com/> .

### 3. RDF/XML Notation
> <xml version=“1.0“ encoding=“utf-8“>
> <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#“
> xmlns:foaf=“http://xmlns.com/foaf/0.1/“ >
> <rdf:Description rdf:about=“http://harald.sack.de/foaf.rdf#harald“>
> <foaf:phone>++49-331-5509-927</foaf:phone>
> </rdf:Description>
> <rdf:Description rdf:about=“http://harald.sack.de/foaf.rdf#harald“>
> <foaf:weblog>
> <rdf:Description rdf:about=“http://haraldblogspot.com/“></rdf:Description>
> </foaf:weblog>
> </rdf:Description>
> </rdf:RDF>




### From a technical point of view, the Semantic Web consists primarily of three technical standards:
•	RDF (Resource Description Framework): The data modeling language for the Semantic Web. All Semantic Web information is stored and represented in the RDF.

•	SPARQL (SPARQL Protocol and RDF Query Language): The query language of the Semantic Web. It is specifically designed to query data across various systems.

•	OWL (Web Ontology Language) The schema language, or knowledge representation (KR) language, of the Semantic Web. OWL enables you to define concepts composably so that these concepts can be reused as much and as often as possible. Composability means that each concept is carefully defined so that it can be selected and assembled in various combinations with other concepts as needed for many different applications and purposes.



### * With data-backed Web applications, the Semantic Web infrastructure allows the data to drive the presentation so that various webpages (presentations) can provide views into a consistent body of information. In this way, the Semantic Web helps data not be so dumb.

### Semantic Web / Linked Data as a distributed framework for the cutting edge technologies.
### 1. “The suite of technologies developed in the Semantic Web … such as ontologies, semantic annotation, Linked Data and semantic Web services … can be used as principal solutions for the purpose of realizing the IoT,” they state. “Defining an ontology and using semantic descriptions for data will make it interoperable for users and stakeholders that share and use the same ontology.”
* 

### 






---------------------------------------------------------------
is symbols can refer to things in the world, how can we
build models from those symbols that help us to capture, understand, and
communicate what we know about relationships between those things?
Blockchain is a data structure, which is arrange of data in computer memory, such as Excel sheet, Google Doc and PDF files.

Suppose that we have a book, in which each page make reference for the previous page through a page number one less than a current page number. We can detect and identify the removal of a page when a page has been removed through the page number.

| Book Ordering | Block Ordering |
|--------------|---------------|
| Page 1,2,3,4,5 | Block "k98ugO" built on "48m775", Block "m448utO" built on "88m795", Block "5l8ugO" built on "87m885" | 
| Implicit that the page buids on the pages whose umber is one less(page 5 builds on page 4)(5 minus 1) | "48m775", "88m795", "87m885" represent fingerprints or hashes of the blocks.  | 

![Blocks in chain refer to previous blocks like books]({{http://www.patternics.com}}/blockchain/image/bl1.JPG)

Also, we can detect the alteration of contents of specific page through page number.
>If anyone changes the content of the page,  then the next page number will not match. 
>since the page number is produced by crunching the content of the previous page.    

![Blocks Detailed]({{http://www.patternics.com}}/blockchain/image/bl2.JPG)

Blockchain is in same shooses, each block is built on top of the recent block and use its
previous block’s content as a signature. Building a block & adding it in the Blockchain is the task of the miner nodes

* In public Blockchain it is made computationally difficult to add a block to prevent
attacks.

* Miners try to guess a number in such a way that if it gets crunched with the most
recent block’s fingerprint than it will create a new fingerprint which will be less that the
last/most recent block in the Blockchain.

* It takes time & computational power to add a Block in the Blockchain. Hence there is
some reward (25 BTC in case of Bitcoin Blockchain)

* Private Blockchain can chose other methods to add a block as they can trust the
miners using a contract etc.

### What is Smart Contract?
#### Smart contract is a term used to describe computer program code that is capable of facilitating, executing, and enforcing the negotiation or performance of an agreement (i.e. contract) using blockchain technology.

* The entire process is automated can act as a complement, or substitute, for legal contracts, where the terms of the smart contract are recorded in a computer language as a set of instructions.

### What is Ethereum Virtual Machine ?
* Ethereum is a programmable Blockchain
* It allows user to create their own operations
* Ethereum in the narrow sense refers to a suite of protocols that define a platform for decentralized applications.
* At the heart of it is the Ethereum Virtual Machine (“EVM”), which can execute code of arbitrary algorithmic complexity.
* In computer science terms, Ethereum is “Turing complete”.
* Developers can create applications that run on the EVM using friendly programming languages modelled on existing languages like JavaScript and Python.

### What is SOLIDITY?
* High-level object-oriented language for smart contratcs
* Solidity was initially proposed in August 2014 by Gavin Wood
* Solidity lets you program on Ethereum, a blockchain-based virtual machine
* Solidity is a statically typed programming language
* A Contract programming language that has similarities to Javascript and C
* Contract-specific features include modifier (guard) clauses, event notifiers for listeners, and custom global variables.
* Solidity is compiled to bytecode that is executable on the EVM

# Click below link for Ethereum Solidity programming, Bitcoin Programming !

## [Making New Cryptocurrency using Ethereum Blockchain and SOLIDITY](http://www.patternics.com/blockchain/create_new_cryptocurrency)

## [Smart Contract programming using Ethereum SOLIDITY](http://www.patternics.com/blockchain/smart_contract)

## [Bitcoin concept and programming](http://www.patternics.com/blockchain/bitcoin)

## Installation and usage
Program is written in java, solidity. it one may need solidity shoulde be installed ( https://docs.continuum.io/anaconda/install ) or install python 2.7 and then install Numpy, Scipy, Pandas, matplotlib,jupyter manually as follows.
#### Remix
If you just want to try Solidity for small contracts, you can try Remix which does not need any installation. If you want to use it without connection to the Internet, you can go to https://github.com/ethereum/browser-solidity/tree/gh-pages and download the .ZIP file as explained on that page.

#### npm / Node.js
This is probably the most portable and most convenient way to install Solidity locally.

A platform-independent JavaScript library is provided by compiling the C++ source into JavaScript using Emscripten. It can be used in projects directly (such as Remix). Please refer to the solc-js repository for instructions.

It also contains a commandline tool called solcjs, which can be installed via npm:

> npm install -g solc

#### Docker
We provide up to date docker builds for the compiler. The stable repository contains released versions while the nightly repository contains potentially unstable changes in the develop branch.

> docker run ethereum/solc:stable solc --version

### Meta

> Acknowledgement : Some images and articles are from other sites or materials: Amelie Gyrard: Christian Bonnet (Eurecom, Mobile Communication)

Yoonsu Park - http://www.patternics.com Distributed under the MIT license. See LICENSE for more information( https://en.wikipedia.org/wiki/MIT_License ). https://github.com/blockchain99/blockchain
