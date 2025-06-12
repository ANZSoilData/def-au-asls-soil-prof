# def-au-asls-soil-prof
Machine-readable representation of the classifiers described in chapter 8 Soil Profile, by R.C. McDonald and R.F. Isbell, in Australian soil and land survey field handbook (3rd edn)

This work supersedes: Cox, Simon; & Gregory, Linda (2020): RDF representation of ASLS soil profile classification. v1. CSIRO. Data Collection. https://doi.org/10.25919/5f42f324b2ef8

## Preparing the vocabulary for loading in RVA

All collection members must have an `rdf:type`, else they won't render in the RVA browse view. 
All resources must have an `rdfs:label` or `skos:prefLabel`, else they won't have nice titles in the RVA browse view. 

Since `ASLS Land Surface` imports some concepts and collections from `ASLS Substrate`, the `rdf:type` and `skos:prefLabel` for the linked elements must be available locally, not just through the `owl:imports`. 

Run this SPARQL prior to loading:
```
INSERT  { ?m a ?t ; skos:prefLabel ?l .}
WHERE {
	?c skos:member ?m . 
	?m a ?t ; 
	      skos:prefLabel ?l .
}
```

Contact: 

[Linda Gregory](https://orcid.org/0000-0002-0693-1899)
linda.gregory@csiro.au 
