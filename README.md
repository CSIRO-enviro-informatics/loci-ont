# LOC-I Ontology
A profile of several ontologies implemented to govern Linked Data resources published within the LOC-I project.

This is a profile of the [GeoSPARQL](http://www.opengeospatial.org/standards/geosparql) and [DCAT v2](https://www.w3.org/TR/vocab-dcat-2/) & [VOID](http://www.w3.org/TR/void/) that require certain properties defined by those ontologies be present for several classes of resource that are of particular importance to the [LOC-I](https://confluence.csiro.au/display/DIPAAnalyticHubs/Location+Integration+Capability+Loc-I) project.

This ontology constrains both normative instruction on what constitutes LOC-I objects and supplies executable constraints to validate instances.


## Contents
The resources in this profile are:
* **[model.html](model.html)** - normative definitions of classes defined by this ontology that are equivalent to constrained vclasses defined by ontologies this profiles
* **[model.ttl](model.ttl)** - RDF version of the model
* **[profile.ttl](profile.ttl)** - a formal description of how this ontology profiles other ontologies, using the [Profiles Ontology](https://w3c.github.io/dxwg/profilesont/)
* **[constraints-shacl.ttl](constraints-shacl.ttl)** - RDF data shape constraints using the [Shapes Constraint Language, SHACL](https://www.w3.org/TR/shacl/) to be used to validate LOC-I class & property instances


## License
The content of this API is licensed for use under the [Creative Commons 4.0 License](https://creativecommons.org/licenses/by/4.0/). See the [license deed](LICENSE) all details.


## Citation
If you wish to cite this profile, please do so like this:

Car, N.J. (2018) "LOC-I Ontology". An OWL ontology and profile of other ontologies. http://linked.data.gov.au/def/loci


## Contacts
*author*:  
**Nicholas Car**  
CSIRO Land & Water, Environmental Informatics Group  
<nicholas.car@csiro.au>
