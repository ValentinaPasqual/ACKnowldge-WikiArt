# ACKnowldge-WikiArt
## Analysis on Complex Knowledge over Wikidata works of Art


## Scope

## Methodology

All artworks with their type.

From Wikidata SPARQL endpoint, we selected all artworks (Q1). Then we got all artworks related metadata from Wikidata API (```wbgetentities``` method). 
This process is available at ```get_all_artworks.py```. 

Q1: All entities belonging to work of art subclasses
```
SELECT DISTINCT ?artwork ?type WHERE {
    ?artwork wdt:P31 ?type.
    ?type (wdt:P279*) wd:Q838948. hint:Prior hint:rangeSafe true
}
``` 

The dataset contains now all works of art stored in Wikidata (until 14/04/2022). 
We semiautomatically surveyed the existing classes and removed all elements belonging to musical, cinematographic classes and statistical rumor.
This phase of pre-processing can be found at ```dataset_preprocessing.ipynb```.


