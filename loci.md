# Loc-I Ontology
Markdown documentation created by [pyLODE](http://github.com/rdflib/pyLODE)


## Metadata
* **IRI**
  * `http://linked.data.gov.au/def/loci`
* **Creators(s)**
  * <a href='https://orcid.org/0000-0002-3884-3420'>Simon J D Cox, CSIRO</a>
  * <a href='http://orcid.org/0000-0002-8742-7730'>Nicholas J Car, Surround Australia</a>
* **Created**
  * 2018-10-29
* **Modified**
  * 2020-02-04
* **Version Information**
  * Beta version
* **Version IRI**
  * <a href="http://linked.data.gov.au/def/loci/1.1">http://linked.data.gov.au/def/loci/1.1</a>
* **Imports**
  * <a href="http://vocab.deri.ie/void">http://vocab.deri.ie/void</a>
  * <a href="http://linked.data.gov.au/def/geox">http://linked.data.gov.au/def/geox</a>
  * <a href="http://www.w3.org/ns/dcat#">dcat:</a>
  * <a href="http://www.w3.org/ns/dcat">http://www.w3.org/ns/dcat</a>
  * <a href="http://xmlns.com/foaf/0.1/">foaf:</a>
* **Ontology Source**
  * <a href="loci.ttl">RDF (turtle)</a>
* **Code Repository**
  * <https://github.com/CSIRO-enviro-informatics/loci-ont>
### Description
<p>An ontology to govern Linked Data resources published within the <a href="https://confluence.csiro.au/display/DIPAAnalyticHubs/Location+Integration+Capability+Loc-I">Loc-I</a> project.</p>
<p>The primary focus is on (a) datasets composed of multiple geospatial features (objects); (b) recording relationships between features, with metadata attached to reified rdf:Statements. </p>

## Table of Contents
1. [Classes](#classes)
1. [Object Properties](#objectproperties)
1. [Properties](#properties)
1. [Namespaces](#namespaces)  


## Overview
![Loc-I ontology overview](./images/loci.png)
**Figure 1:** Ontology overview  
## Classes
[Loc-I Data Publishers](#Loc-IDataPublishers),
[Loc-I Dataset](#Loc-IDataset),
[Loc-I Dataset Linking Statement](#Loc-IDatasetLinkingStatement),
[Loc-I Feature](#Loc-IFeature),
[Loc-I Linkset](#Loc-ILinkset),
### Loc-I Data Publishers <sup>c</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#DataPublisher`
Description | The set of all approved publishers of Loc-I data, all of whom are known
Super-classes |<a href="http://xmlns.com/foaf/0.1/Group">foaf:Group</a><sup class="sup-c" title="class">c</sup><br />
### Loc-I Dataset <sup>c</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#Dataset`
Description | A Loc-I Dataset is a DCAT and VOID Dataset that has been accepted by the Loc-I Registry Manager.
Super-classes |<a href="http://rdfs.org/ns/void#Dataset">void:Dataset</a><sup class="sup-c" title="class">c</sup><br /><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#Bag">rdf:Bag</a><sup class="sup-c" title="class">c</sup><br /><a href="http://www.w3.org/ns/dcat#Dataset">dcat:Dataset</a><sup class="sup-c" title="class">c</sup><br />
Restrictions |<a href="http://www.w3.org/2000/01/rdf-schema#member">rdfs:member</a> <span class="cardinality">only</span> (<a href="#Loc-IFeature">loci:Feature</a><sup class="sup-c" title="class">c</sup> or <a href="#Loc-IDatasetLinkingStatement">loci:LinkingStatement</a><sup class="sup-c" title="class">c</sup>)<br /><a href="http://purl.org/dc/terms/issued">dcterms:issued</a> <span class="cardinality">exactly</span> 1<br /><a href="http://purl.org/dc/terms/title">dcterms:title</a> <span class="cardinality">exactly</span> 1<br /><a href="http://purl.org/dc/terms/publisher">dcterms:publisher</a> <span class="cardinality">exactly</span> 1 <a href="http://www.w3.org/ns/org#Organization">org:Organization</a><sup class="sup-c" title="class">c</sup><br /><a href="http://purl.org/dc/terms/modified">dcterms:modified</a> <span class="cardinality">exactly</span> 1<br /><a href="http://www.w3.org/ns/dcat#contactPoint">dcat:contactPoint</a> <span class="cardinality">min</span> 1<br />
Sub-classes |<a href="#Loc-ILinkset">loci:Linkset</a><sup class="sup-c" title="class">c</sup><br />
### Loc-I Feature <sup>c</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#Feature`
Description | A Loc-I Feature is a GeoSPARQL Feature that has at least one Geometry
Super-classes |<a href="http://www.opengis.net/ont/geosparql#Feature">geo:Feature</a><sup class="sup-c" title="class">c</sup><br />
Restrictions |<a href="http://www.opengis.net/ont/geosparql#hasGeometry">geo:hasGeometry</a> <span class="cardinality">min</span> 1 <a href="http://www.opengis.net/ont/geosparql#Geometry">geo:Geometry</a><sup class="sup-c" title="class">c</sup><br />
### Loc-I Dataset Linking Statement <sup>c</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#LinkingStatement`
Description | An RDF Statement (Subject, Predicate, Object + additional metadata) that links class instances in one Loc-I Dataset with class instances in another
Super-classes |<a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#Statement">rdf:Statement</a><sup class="sup-c" title="class">c</sup><br />
Restrictions |<a href="#hadgenerationmethod">loci:hadGenerationMethod</a><sup class="sup-op" title="object property">op</sup> <span class="cardinality">exactly</span> 1 <a href="http://www.w3.org/ns/prov#Plan">prov:Plan</a><sup class="sup-c" title="class">c</sup><br /><a href="#ismemberof">loci:isMemberOf</a><sup class="sup-op" title="object property">op</sup> <span class="cardinality">exactly</span> 1 <a href="#Loc-ILinkset">loci:Linkset</a><sup class="sup-c" title="class">c</sup><br />
### Loc-I Linkset <sup>c</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#Linkset`
Description | A Loc-I Linkset is a specialised form of a VoID Linkset that requires the void:subjectsTarget & void:objectsTarget indicate Loc-I Datasets
Super-classes |<a href="#Loc-IDataset">loci:Dataset</a><sup class="sup-c" title="class">c</sup><br /><a href="http://rdfs.org/ns/void#Linkset">void:Linkset</a><sup class="sup-c" title="class">c</sup><br />
Restrictions |<a href="http://www.w3.org/2000/01/rdf-schema#member">rdfs:member</a> <span class="cardinality">only</span> <a href="#Loc-IDatasetLinkingStatement">loci:LinkingStatement</a><sup class="sup-c" title="class">c</sup><br />

## Object Properties
[had generation method](hadgenerationmethod),
[is member of](ismemberof),
[](hadgenerationmethod)
### had generation method <sup>op</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#hadGenerationMethod`
Description | The method that was used to generate this object
Domain(s) |<a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#Statement">rdf:Statement</a><sup class="sup-c" title="class">c</sup><br />
Range(s) |<a href="http://www.w3.org/ns/prov#Plan">prov:Plan</a><sup class="sup-c" title="class">c</sup><br />
[](ismemberof)
### is member of <sup>op</sup>
Property | Value
--- | ---
IRI | `http://linked.data.gov.au/def/loci#isMemberOf`
Description | In principle this is just inverse of rdfs:member, but because it is defined in a local namespace, make it a sub-property of the inverse

## Properties
[None](None),
[](None)
### None <sup>p</sup>
Property | Value
--- | ---
IRI | `ub1bL210C22`

## Namespaces
* **default (:)**
  * `http://linked.data.gov.au/def/loci#`
* **dcat**
  * `http://www.w3.org/ns/dcat#`
* **dcterms**
  * `http://purl.org/dc/terms/`
* **doap**
  * `http://usefulinc.com/ns/doap#`
* **foaf**
  * `http://xmlns.com/foaf/0.1/`
* **geo**
  * `http://www.opengis.net/ont/geosparql#`
* **geox**
  * `http://linked.data.gov.au/def/geox#`
* **loci**
  * `http://linked.data.gov.au/def/loci#`
* **org**
  * `http://www.w3.org/ns/org#`
* **owl**
  * `http://www.w3.org/2002/07/owl#`
* **prof**
  * `http://www.w3.org/ns/dx/prof/`
* **prov**
  * `http://www.w3.org/ns/prov#`
* **rdf**
  * `http://www.w3.org/1999/02/22-rdf-syntax-ns#`
* **rdfs**
  * `http://www.w3.org/2000/01/rdf-schema#`
* **sdo**
  * `https://schema.org/`
* **skos**
  * `http://www.w3.org/2004/02/skos/core#`
* **void**
  * `http://rdfs.org/ns/void#`
* **xml**
  * `http://www.w3.org/XML/1998/namespace`
* **xsd**
  * `http://www.w3.org/2001/XMLSchema#`

## Legend
* Classes: c
* Object Properties :op
* Functional Properties: fp
* Data Properties: dp
* Annotation Properties: dp
* Properties: p
* Named Individuals: ni