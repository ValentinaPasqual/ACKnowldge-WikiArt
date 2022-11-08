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
We semiautomatically surveyed the existing classes and removed all elements belonging to musical, cinematographic classes and statistical rumor. In the dataset are still comprised all instances of classes belonging literary productions, visual artworks, cultural sites, operatic works, performing arts, journals etc.
This phase of pre-processing can be found at ```dataset_preprocessing.ipynb```. 

The obtained dataset contains XXX entitites belonging to XXX classes and described by XXXX statements. The dataset (XXX GB) is stored in XXX json files, each listing 50 entities with their statements. The dataset is available at XXXX.

