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

### From a technical point of view, the Semantic Web consists primarily of three technical standards(RDF, SPARQL, OWL):

•	RDF (Resource Description Framework): The data modeling language for the Semantic Web. All Semantic Web information is stored and represented in the RDF.

•	SPARQL (SPARQL Protocol and RDF Query Language): The query language of the Semantic Web. It is specifically designed to query data across various systems.

&nbsp;  A Query Language for RDF Graph Traversal (SPARQL Query Language Specification)

&nbsp;  A Protocol Layer, to use SPARQL via http (SPARQL Protocol for RDF Specification)

&nbsp;  An XML Output Format Specification for SPARQL Queries (SPARQL Query XML Results Format)

•	OWL (Web Ontology Language) The schema language, or knowledge representation (KR) language, of the Semantic Web. OWL enables you to define concepts composably so that these concepts can be reused as much and as often as possible. Composability means that each concept is carefully defined so that it can be selected and assembled in various combinations with other concepts as needed for many different applications and purposes.

## There are three ways of Semantic Web notations as follows.

> Subject X is "Harald" and Object(Literal) Y is "++49-331-5509-927", which is “the value of X,” and Predicate, P is “phone”

> Subject X is "Harald" and Object(Resource) Y is "http://harald.blogspot.com/", which is “the value of X,” and Predicate, P is “weblog”

![semantic web graph](./image/rdf1.JPG)

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

![semantic web graph:rdf2](./image/rdf2.JPG)

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

![semantic web graph:rdf2](./image/rdf4.JPG)

> @prefix hpi-lv: <http://hpi-web.de/Lecture#>.<br />
> <http://hpi-web.de/Spring14#KE> hpi-lv:name "Knowledge Engineering";<br />
> hpi-lv:takesPlace [<br />
> hpi-lv:date "Tue 13.30-15.00";<br />
> hpi-lv:room "HS3" ] .

* Deferencable Blank Nodes

![semantic web graph:rdf2](./image/rdf5.JPG)

> @prefix hpi-lv: <http://hpi-web.de/Lecture#>.<br />
> <http://hpi-web.de/Spring14#KE> hpi-lv:name "Knowledge Engineering";<br />
> hpi-lv:takesPlace _:ID1 .<br />
> _:ID1 hpi-lv:date "Tue 13.30-15.00";<br />
> hpi-lv:room "HS3" .

#### * RDF-Collection

![RDF-Collection](./image/rdf6.JPG)

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

![RDF-statement](./image/rdf_st.JPG)

Sherlock Holmes supposes that the Gardener has killed the Butler

![RDF-statement](./image/rdf_st2.JPG)

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



## RDF Schema

![RDF-schema](./image/rdfschema.JPG)

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

![RDF-property](./image/prop.JPG)

• rdfs:subClassOf is transitive property to define inheritance hierarchies for classes

• rdfs:subPropertyOf is transitive property to define inheritance hierarchies for properties

• rdfs:domain is defines the domain of a property concerning a class

• rdfs:range is defines range of a property concerning a class

![RDF-property2](./image/prop2.JPG)

![RDF-property3](./image/prop3.JPG)

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

![RDF-property4](./image/prop4.JPG)


## SPARQL Progrmming
### Click Following link for further SPARQL(Protocol and RDF Query Language) Progamming !

#### 1. Select all authors with their notable works and year of publication <br>
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

#### 2. Select all authors with their notable works and year of publication <br>
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

#### 3. Select all authors with their notable works and year of publication <br>
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

#### 4. How many authors are there in DBpedia? <br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT (COUNT(?author)) AS ?num<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer .<br>
}
</blockquote> 

#### 5. How many distinct authors are there in DBpedia who have entries for notable works? <br>
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

#### 6. Which author wrote how many notable works?
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
</blockquote>

#### 7. Select all authors, who they are influenced by and all the influencers notable works<br>
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

#### 8. Select all authors, who don‘t have a notable work entry in DBpedia <br>
Filtering of query solutions is done within a FILTER expression using NOT EXISTS and EXISTS.<br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT ?author<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer<br>
&emsp; FILTER NOT EXISTS {?author dbpedia-owl:notableWork ?work .}<br>
}
</blockquote>

#### 9.Select all authors, who don‘t have a notable work entry in DBpedia<br>
Filtering of query solutions be removing possible solutions with MINUS.<br>
<blockquote>PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#><br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/><br>
SELECT ?author<br>
FROM <http://dbpedia.org/><br>
WHERE {<br>
&emsp; ?author rdf:type dbpedia-owl:Writer<br>
&emsp; MINUS {?author dbpedia-owl:notableWork ?work .} <br>
}
</blockquote>

#### 10 Property Paths <br>
A property path is a possible route through an RDF graph between two graph nodes.

• trivial case: property path of length 1, i.e. a triple pattern

• alternatives: match one or both possibilities
&emsp; { :book1 dc:title|rdfs:label ?displayString }

• sequence: property path of length >1
&emsp; { ?x foaf:mbox <mailto:alice@example> .<br>
&emsp; &emsp; ?x foaf:knows/foaf:knows/foaf:name ?name . }

• inverse property paths: reversing the direction of the triple
&emsp; { ?x foaf:mbox <mailto:alice@example> }<br>
&emsp; &emsp;  =<br>
&emsp; { <mailto:alice@example> ^foaf:mbox ?x }

• inverse path sequences paths <br>
{ ?x foaf:knows/^foaf:knows ?y . <br>
&emsp; FILTER(?x != ?y) }
![RDF-property path](./image/propp.JPG)

• arbitrary length match
{ ?x foaf:mbox <mailto:alice@example> .<br>
&emsp; ?x foaf:knows+/foaf:name ?name . }
![RDF-property path2](./image/propp2.JPG)

• inverse path sequences paths
&emsp; { ?x foaf:knows/^foaf:knows ?y . 
&emsp; &emsp; FILTER(?x != ?y) }

• arbitrary length match
&emsp; { ?x foaf:mbox <mailto:alice@example> .
&emsp; &emsp; ?x foaf:knows+/foaf:name ?name . }

• negated property paths
&emsp; { ?x !(rdf:type|^rdf:type) ?y } 

### Who are the authors who were influenced by the influencers of George Orwell? <br>
<blockquote>PREFIX : <http://dbpedia.org/resource/> <br>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> <br>
PREFIX dbpedia-owl: <http://dbpedia.org/ontology/> <br>
SELECT ?influencedByInfluencers <br>
FROM <http://dbpedia.org/> <br>
WHERE { <br>
:George_Orwell  <br>
dbpedia-owl:influencedBy/^dbpedia-owl:influencedBy <br>
?influencedByInfluencers . <br>
}
</blockquote>

## OWL(Web Ontology Language)

### What is Ontology and OWL(Web Ontology Language)?
RDF data can be encoded with semantic metadata using two syntaxes: RDFS(RDF Schema) and OWL.

Ontology classifies things in terms of semantics, or meaning into class or subclass, which allow us to define contextual relationship behind a defined vocabulary.

OWL is the formal syntax for defining ontologies and it is extension of RDFS(RDF Schema)

### Ontology axioms consist of the following three building blocks:<br>
• Classes : comparable with classes in RDFS<br>
• Individuals : comparable with objects in RDFS<br>
• Properties : comparable with properties in RDFS

1.OWL – Classes

• there exist two predefined classes

• owl:Thing (class that contains all individuals)

> owl:Nothing (empty class)
> Definition of a class  

> :Book a owl:Class .

2.OWL – Individuals

• Definition of individuals via class membership(a "NineteenEightyfour" Book instance generated)

> :NineteenEightyfour a :Book .

• Individuals can also be defined without direct class membership as named entity

> :HaraldSack a owl:NamedIndividual .

3.OWL – Properties

There exist two property variants: object properties and datatype properties

• Object properties are defined like classes 

> :author a owl:ObjectProperty .

&emsp; • Domain and Range of object properties<br>
<blockquote> :author a owl:ObjectProperty ;
&emsp; rdfs:domain :Book ;<br>
&emsp; rdfs:range :Writer .
</blockquote> 
 


### 1. OWL example
@prefix : <http://example.com/owl/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
:HappyPerson a owl:Class ;
    owl:equivalentClass [
    a owl:Class ;
    owl:intersectionOf ([ a owl:Restriction ;
                                            owl:onProperty :hasChild ;
                                            owl:allValuesFrom :HappyPerson ]
                                         [ a owl:Restriction ;
                                           owl:onProperty :hasChild ;
                                           owl:someValuesFrom :HappyPerson ]
                                          )
                      ].

![OWL1](./image/owl.JPG)


## [Click for further SPARQL Progamming !](https://github.com/blockchain99/SemanticWeb)


> Acknowledgement : Some images and articles are from other sites or materials: Amelie Gyrard: Christian Bonnet (Eurecom, Mobile Communication),Dr. Harald Sack : Hasso-Plattner-Institut for IT Systems Engineering, Dean Allemang : Semantic Web for the Working
Ontologist

## Meta
Yoonsu Park - http://www.patternics.com Distributed under the MIT license. See LICENSE for more information( https://en.wikipedia.org/wiki/MIT_License ). https://github.com/blockchain99/SemanticWeb
