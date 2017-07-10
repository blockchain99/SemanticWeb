### Ask not “How can we make the Web infrastructure smarter?” 
## But ask “What can the Web infrastructure provide to improve the consistency and availability of Web data?"
A Connected Web Is a Smarter Web.<BR>
<BLOCKQUOTE>“we need a Web infrastructure that lets us connect data to smart Web applications
so that the whole Web experience is enhanced. The Web seems smarter because smart applications can get the data they need.
</BLOCKQUOTE>

### When we speak of “semantics” of natural language, we often refer to something about what it means to understand the utterance—how to go from the structured letters or sounds in a language to some kind of meaning behind them.

* That is, given that symbols can refer to things in the world, how can we build models from those symbols that help us to capture, understand, and communicate what we know about relationships between those things?

* In the Semantic Web we refer to the things in the world as resources; a resource can be anything that someonemight want to talk about.
Followings are all examples of things someonemight talk about and that can be resources in the SemanticWeb.

### With data-backed Web applications, the Semantic Web infrastructure allows the data to drive the presentation so that various webpages (presentations) can provide views into a consistent body of information. In this way, the Semantic Web helps data not be so dumb.

## There are three ways of Semantic Web notations as follows.

> Subject X is "Harald" and Object(Literal) Y is "++49-331-5509-927", which is “the value of X,” and Predicate, P is “phone”

> Subject X is "Harald" and Object(Resource) Y is "http://harald.blogspot.com/", which is “the value of X,” and Predicate, P is “weblog”

![semantic web graph]({{http://www.patternics.com}}/SemanticWeb/image/rdf1.JPG)

### 1.  N-Triples Notation

• URIs/IRIs in angle brackets

• Literals in quotation marks

• Triple ends with a period

> <http://harald.sack.de/foaf.rdf#harald> <http://xmlns.com/foaf/0.1/phone> “+ <br />
> +49-331-5509-927“ .<br />
> <http://harald.sack.de/foaf.rdf#harald> <http://xmlns.com/foaf/0.1/weblog><br />
> <http://harald.blogspot.com/> .

### 2. Turtle (Terse RDF Tripel Language) Notation
> @prefix foaf: <http://xmlns.com/foaf/0.1/> .<br />
> @base <http://harald.sack.de/foaf.rdf><br />
> <#harald> foaf:phone “++49-331-5509-927“ .<br />
> <#harald> foaf:weblog <http://harald.blogspot.com/> .

* Below "Turtle Notation with ;" has same result with above Trutle Notation : semicolon indicates that subsequent triples have the same subject

> @prefix foaf: <http://xmlns.com/foaf/0.1/> .<br />
> @base <http://harald.sack.de/foaf.rdf><br />
> <#harald> foaf:phone “++49-331-5509-527“ ; foaf:weblog <http://semweb2014.blogspot.com/> .

![semantic web graph:rdf2]({{http://www.patternics.com}}/SemanticWeb/image/rdf2.JPG)

* comma indicates that subsequent triples have same subject and property (object list)

> @prefix foaf: <http://xmlns.com/foaf/0.1/> .<br />
> <#harald> foaf:weblog <http://semweb2014.blogspot.com/> ,<br />
> <http://semweb2013.blogspot.com/> ,<br />
> <http://semweb2012.blogspot.com/> .<br />

* Typed literal

![semantic web graph:rdf2]({{http://www.patternics.com}}/SemanticWeb/image/rdf3.JPG)

> @prefix lec: <http://hpi-web.de/Lecture#> .<br />
> <http://hpi.web.de/Spring14#KE><br />
> lec:name “Knowledge Engineering“^^<http://www.w3c.org/2001/XMLSchema#string> ;<br />
> lec:hours “4“^^<http://www.w3c.org/2001/XMLSchema#integer> .<br />

* Anonymous Blank Nodes

![semantic web graph:rdf2]({{http://www.patternics.com}}/SemanticWeb/image/rdf4.JPG)

> @prefix hpi-lv: <http://hpi-web.de/Lecture#>.<br />
> <http://hpi-web.de/Spring14#KE> hpi-lv:name "Knowledge Engineering";<br />
> hpi-lv:takesPlace [<br />
> hpi-lv:date "Tue 13.30-15.00";<br />
> hpi-lv:room "HS3" ] .

* Deferencable Blank Nodes

![semantic web graph:rdf2]({{http://www.patternics.com}}/SemanticWeb/image/rdf5.JPG)

> @prefix hpi-lv: <http://hpi-web.de/Lecture#>.<br />
> <http://hpi-web.de/Spring14#KE> hpi-lv:name "Knowledge Engineering";<br />
> hpi-lv:takesPlace _:ID1 .<br />
> _:ID1 hpi-lv:date "Tue 13.30-15.00";<br />
> hpi-lv:room "HS3" .

#### * RDF-Collection

![RDF-Collection]({{http://www.patternics.com}}/SemanticWeb/image/rdf6.JPG)

> @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .<br />
> @prefix lv: <http://hpi-web.de/Lecture#> .<br />
> @base <http://hpi-web.de/>.<br />
> <Sprint14#KE> lv:hasParticipant [<br />
> rdf:first <BurgerAnton>; rdf:rest [<br />
> rdf:first <MuellerFranz>; rdf:rest [<br />
> rdf:first <SchmidtJoseph>; rdf:rest [<br />
> rdf:first <SchulzeEgon>;<br />
> rdf:rest rdf:nil<br />
> ] ] ] ] .

#### * RDF-Reification

rdf:Statement defines an RDF Statement, consisting of Subject, Predicate and Object

![RDF-statement]({{http://www.patternics.com}}/SemanticWeb/image/rdf_st.JPG)

Sherlock Holmes supposes that the Gardener has killed the Butler

![RDF-statement]({{http://www.patternics.com}}/SemanticWeb/image/rdf_st2.JPG)

> @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .<br />
> @prefix : <http://example.org/Crimestories#> .<br />
> :SherlockHolmes :supposes :StatementOnGardener .<br />
> :StatementOnGardener a rdf:Statement ;<br />
> rdf:subject :Gardener ;<br />
> rdf:predicate :hasKilled ;<br />
> rdf:object :Butler .


### 3. RDF/XML Notation
> <xml version=“1.0“ encoding=“utf-8“> <br />
> <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#“ <br />
> xmlns:foaf=“http://xmlns.com/foaf/0.1/“ > <br />
> <rdf:Description rdf:about=“http://harald.sack.de/foaf.rdf#harald“> <br />
> <foaf:phone>++49-331-5509-927</foaf:phone> <br />
> </rdf:Description> <br />
> <rdf:Description rdf:about=“http://harald.sack.de/foaf.rdf#harald“> <br />
> <foaf:weblog> <br />
> <rdf:Description rdf:about=“http://haraldblogspot.com/“></rdf:Description><br />
> </foaf:weblog> <br />
> </rdf:Description> <br />
> </rdf:RDF>


> @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .<br />
> @prefix lv: <http://hpi-web.de/Lecture#> .<br />
> @base <http://hpi-web.de/>.<br />
> <Spring14#KE> lv:hasParticipant (<BurgerAnton> <MuellerFranz><br />
> <SchmidtJoseph> <SchulzeEgon>).

### From a technical point of view, the Semantic Web consists primarily of three technical standards:

•	RDF (Resource Description Framework): The data modeling language for the Semantic Web. All Semantic Web information is stored and represented in the RDF.

•	SPARQL (SPARQL Protocol and RDF Query Language): The query language of the Semantic Web. It is specifically designed to query data across various systems.

&nbsp;  A Query Language for RDF Graph Traversal (SPARQL Query Language Specification)

&nbsp;  A Protocol Layer, to use SPARQL via http (SPARQL Protocol for RDF Specification)

&nbsp;  An XML Output Format Specification for SPARQL Queries (SPARQL Query XML Results Format)

•	OWL (Web Ontology Language) The schema language, or knowledge representation (KR) language, of the Semantic Web. OWL enables you to define concepts composably so that these concepts can be reused as much and as often as possible. Composability means that each concept is carefully defined so that it can be selected and assembled in various combinations with other concepts as needed for many different applications and purposes.

## RDF Schema

![RDF-schema]({{http://www.patternics.com}}/SemanticWeb/image/rdfschema.JPG)

### RDFSchema allows following actions.

• Definition of classes

• Class instantiation in RDF via <rdf:type>

• Definition of properties and restrictions

• Definition of hierarchies

• Subclasses and superclasses

• Subproperties and superproperties

### There are two imporrant elements in RDF Schema, They are Classes and Properties.

#### 1. Classes are as follows.

  • rdfs:Class is Concept of a class, defines an abstract object and is applied (with rdf:type) to create instances
 
  • rdf:Propert is Base class for properties
  
  • rdfs:Literal is Class for literals
  
  • rdfs:Resource is every entity of an RDF model is instance of this class
  
  • and additionally,Threre are rdfs:Datatype, rdf:XMLLiteral, rdfs:Container, rdfs:ContainerMembershipProperty in Classes.

#### 2. Properties are as follows.

![RDF-property]({{http://www.patternics.com}}/SemanticWeb/image/prop.JPG)

• rdfs:subClassOf is transitive property to define inheritance hierarchies for classes

• rdfs:subPropertyOf is transitive property to define inheritance hierarchies for properties

• rdfs:domain is defines the domain of a property concerning a class

• rdfs:range is defines range of a property concerning a class

![RDF-property2]({{http://www.patternics.com}}/SemanticWeb/image/prop2.JPG)

![RDF-property3]({{http://www.patternics.com}}/SemanticWeb/image/prop3.JPG)

> @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> . <br />
> @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .<br />
> @prefix : <http://example.org/>.<br />
> :Lecture a rdfs:Class;<br />
> rdfs:subClassOf :Course.<br />
> :Seminar a rdfs:Class ;<br />
> rdfs:subClassOf :Course.<br />
> :Person a rdfs:Class .<br />
> :Staff a rdfs:Class ;<br />
> rdfs:subClassOf :Person .<br />
> :SeniorResearcher a rdfs:Class ;<br />
> rdfs:subClassOf :Staff .<br />
> :Professor a rdfs:Class ;<br />
> rdfs:subClassOf :Staff.<br />
> :isManagedBy a rdf:Property ;<br />
> rdfs:domain :Course ;<br />
> rdfs:range :Staff .<br />
> <Spring14#KE> a :Lecture .<br />
> :HaraldSack a :SeniorResearcher .<br />
> <Spring14#KE> :isManagedBy :HaraldSack .

### What conclusions can we deduce with RDF(S)?

![RDF-property4]({{http://www.patternics.com}}/SemanticWeb/image/prop4.JPG)


## SPARQL Progrmming
### Click Following link for further SPARQL(Protocol and RDF Query Language) Progamming !

1. Select all authors with their notable works and year of publication <br>
<blockquote>  PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> <br>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#> <br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/> <br>
PREFIX dbpprop: <http://dbpedia.org/property/> <br>
SELECT ?author ?work ?date <br>
FROM <http://dbpedia.org/> <br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp; ?author dbpedia-owl:notableWork ?work .<br>
&emsp; ?work dbpprop:releaseDate ?date <br>
} ORDER BY ?date<br>
LIMIT 100         
</blockquote>

2. Select all authors with their notable works and year of publication <br>
New variable is assigned using "xsd:integer(?date) AS ?year" in SELECT phrase. <br>
<blockquote>  PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> <br>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#> <br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/> <br>
PREFIX dbpprop: <http://dbpedia.org/property/> <br>
SELECT ?author ?work xsd:integer(?date) AS ?year <br>
FROM <http://dbpedia.org/> <br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp; ?author dbpedia-owl:notableWork ?work .<br>
&emsp; ?work dbpprop:releaseDate ?date <br>
} ORDER BY ?date<br>
LIMIT 100         
</blockquote> 

3. Select all authors with their notable works and year of publication <br>
New variable is assigned using "(REPLACE(str(?date),"[^0-9]", "")) AS ?year" in SELECT phrase. <br>
<blockquote>  PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> <br>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#> <br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/> <br>
PREFIX dbpprop: <http://dbpedia.org/property/> <br>
SELECT ?author ?work (REPLACE(str(?date),"[^0-9]", "")) AS ?year <br>
FROM <http://dbpedia.org/> <br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp; ?author dbpedia-owl:notableWork ?work .<br>
&emsp; ?work dbpprop:releaseDate ?date <br>
&emsp; FILTER REGEX (?date, "[0-9]{4}") .
} ORDER BY ?date<br>
LIMIT 100         
</blockquote> 

4. How many authors are there in DBpedia? <br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT (COUNT(?author)) AS ?num<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
}
</blockquote> 

5. How many distinct authors are there in DBpedia who have entries for notable works? <br>
Aggregate Functions : (COUNT(DISTINCT ?author)) <br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT (COUNT(DISTINCT ?author)) AS ?num<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp;?author dbpedia-owl:notableWork ?work .<br>
}
</blockquote>

6. Which author wrote how many notable works?
<blockquote>Aggregate Functions : (COUNT(?work)), GROUP BY ?author<br>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT ?author (COUNT(?work)) AS ?num_works<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp; ?author dbpedia-owl:notableWork ?work .<br>
} GROUP BY ?author <br>
ORDER BY DESC (?num_works)

7. Select all authors, who they are influenced by and all the influencers notable works<br>
Subqueries : <br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT ?author ?influencer ?work<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
{ SELECT ?author ?influencer<br>
&emsp; FROM <http://dbpedia.org/><br>
&emsp; WHERE {<br>
&emsp; &emsp; ?author rdf:type dbpedia-owl:Writer .<br>
&emsp; &emsp; ?author dbpedia-owl:influencedBy ?influencer .<br>
} LIMIT 10<br>
}<br>
&emsp; ?influencer dbpedia-owl:notableWork ?work .<br>
}
</blockquote>



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
