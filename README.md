# ACKnowldge-WikiArt
## Analysis on Complex Knowledge over Wikidata works of Art


## Scope

## Methodology

All artworks with their type.

From Wikidata SPARQL endpoint, we selected all artworks (Q1). Then we got all artworks related metadata from Wikidata API (```wbgetentities``` method). 
This process is available at ```get_all_artworks.py```. [extraction date 01/05/2022]

Q1: All entities belonging to work of art subclasses
```
SELECT DISTINCT ?artwork ?type WHERE {
    ?artwork wdt:P31 ?type.
    ?type (wdt:P279*) wd:Q838948. hint:Prior hint:rangeSafe true
}
``` 
The dataset comprises literary productions, visual artworks, cultural sites, operatic works, performing arts, journals etc. We semiautomatically surveyed the existing Wikidata subclasses of work of art and removed all elements belonging to music and cinematographic domains as well as statistical rumor. This phase of pre-processing can be found at ```dataset_preprocessing.ipynb```. 

The dataset contains 2'156'363 works of art (wikidata entities) described by 18'924'333 statements and belonging to 6'612 selected classes. The dataset is stored in a zip folder organised in 10'782 json files, each storing 200 entities and their metadata. The dataset can be found in Zenodo at [![DOI(https://zenodo.org/badge/DOI/10.5281/zenodo.7307852.svg)](https://doi.org/10.5281/zenodo.7307852).



