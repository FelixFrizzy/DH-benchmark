# DH Benchmark Dataset for Ontology Matching

## Description

This is a benchmark dataset for ontology matching in the field of Digital Humanities (DH) created by Felix Ernst. You can find all the general information about the dataset that you need for using it at the [OAEI](https://oaei.ontologymatching.org/) in this repository.
For further information on the [OAEI 2024](http://oaei.ontologymatching.org/2024/) see also [here](https://felixfrizzy.github.io/DH-benchmark/).   
This benchmark dataset facilitaes the development of ontology matching systems for the Humanities, which face special obstacle which are at least partly addressed in this dataset:

- wide range of (historical) languages and writing systems
- domain-specific terms with a small research community at times
- use of a data model suitable for easily creating knowledge organization systems

## Test Cases

The dataset includes several test cases grouped into three sub-domains. Each test case consists of a source ontology, a target ontology and a manually compiled reference alignment. Only equivalent relations ("=") are targeted.

### Archaeology (foldername "arch...")

There were five different vocabularies used for the four different archaeology test cases:
- [DEFC](https://vocabs.dariah.eu/defc_thesaurus/en/) [1]
    - About 800 terms
    - Languages: Mainly English and German
- [PACTOLS](https://isl.ics.forth.gr/bbt-federated-thesaurus/PACTOLS/en/) [2]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[archaeological site](https://ark.frantiq.fr/ark:/26678/pcrt9PJh9aTXv4)" were used
    - About 70 terms
    - Languages: Arabic, Dutch, English, French, German, Italian, Spanish
- [iDAI.world](https://isl.ics.forth.gr/bbt-federated-thesaurus/DAI/en/) [3]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[material things](http://thesauri.da2inst.org/_1c0fa2d2)" were used
    - About 2600 terms
    - Major languages: Arabic, English, French, German, Italian
- [Iron-Age-Danube](https://vocabs.dariah.eu/iad_thesaurus/en/) [4]
    - About 290 terms
    - Languages: Croatian, English, German, Hungarian, Slovenian
- [PARTHENOS](https://vocabs.dariah.eu/parthenos_vocabularies/en/) [5]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[place types](https://isl.ics.forth.gr/parthenos_vocabularies/Concept/32199)" were used
    - About 800 terms
    - Language: English

#### First test case
    - Source: DEFC
    - Target: PACTOLS
    - Reference: 800*70=56000 possible combinations, 11 true positivs (~0,02%)
#### Second test case
    - Source: iDAI.world
    - Target: PACTOLS
    - Reference: 2600*70=182000 possible combinations, 18 true positivs (~0,01%)
#### Third test case
    - Source: Iron-Age-Danube
    - Target: PACTOLS
    - Reference: 290*70=20300 possible combinations, 6 true positivs (~0,03%)
#### Fourth test case
    - Source: PACTOLS
    - Target: PARTHENOS
    - Reference: 70*800=56000 possible combinations, 13 true positivs (~0,02%)

### Cultural History (foldername "cult...")

There were five different vocabularies used for the two different cultural history test cases:
- [iDAI.world](https://isl.ics.forth.gr/bbt-federated-thesaurus/DAI/en/) [3]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[chronology](http://thesauri.dainst.org/_62a09577)" were used
    - About 270 terms
    - Major languages: Arabic, English, French, German, Italian
- [PARTHENOS](https://vocabs.dariah.eu/parthenos_vocabularies/en/) [5]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[Periods](https://isl.ics.forth.gr/parthenos_vocabularies/Concept/7084)" were used
    - About 200 terms
    - Language: English
- [OeAI](https://vocabs.dariah.eu/oeai-cp/en/) [6]
    - About 400 terms
    - Languages: English, German

#### First test case
    - source: iDAI.world
    - target: PARTHENOS
    - Reference: 270*200=54000 possible combinations, 53 true positivs (~0,1%)
#### Second test case
    - source: OeAI
    - target: PARTHENOS
    - Reference: 400*200=80000 possible combinations, 48 true positivs (0,06%)

### DH and Computer Science (foldername "dhcs...")

There were five different vocabularies used for the two different DH/CS test cases:
- [DHA Taxonomy](https://vocabs.dariah.eu/dha_taxonomy/en/) [7]
    - About 115 terms
    - Languages: English
- [UNESCO](https://vocabularies.unesco.org/browser/thesaurus/en/) [8]
    - Adapted version: Only narrower terms and direct ancestors of the concept "[Information and communication](http://vocabularies.unesco.org/thesaurus/domain5)" were used
    - About 490 terms
    - Languages: Arabic, English, French, Russion, Spanish
- [TaDiRAH](https://vocabs.dariah.eu/tadirah/en/) [9]
    - About 170 terms
    - Main Language: English 

#### First test case
    - source: DHA Taxonomy
    - target: UNESCO
    - Reference: 115*490=56350 possible combinations, 12 true positivs (~0,02%)
#### Second test case
    - source: TaDiRAH
    - target: UNESCO
    - Reference: 170*490=83300 possible combinations, 16 true positivs (~0,02%)

## Test Case Design
The following criteria were used to select suitable controlled vocabularies (CVs) from all DH CVs that were found:
- The track should cover different subfields of Humanities
- Preferably specific terminology than general to pose a challenge to the OM systems
- CV is in SKOS format (unlike e.g. plain HTML CVs that could not be used)
- A combination of two CVs needs to have at least some true positivs
- CVs with errors such as doublette terms, terms not in hierarchy, violation of SKOS were not considered

Some potential test cases are hold back for the following OAEI years such that the systems always encounter unseen test cases.

## Reference Alignment Methodology / Provenance
To create a well designed reference alignment, the following points were taken into account:
- Special care was taken to ensure that similar terms are really identical and not closely related, see [10]
- Only the same part-of-speech was considered to be similar (e.g. analysis and to analyse was not considered to be similar)
- Singular and plural was considered to be similar
- Large vocabularies were reduced to only the relevant terms. This means that the branch of the hierarchy containing terms of the desired topic was kept and the other branches was removed. This ensures that the reference alignment can be compiled manually. 
To create the manual alignment, the dataset creator went through each term of the source CV and searched thouroughly for similar terms in the target CV using full text search and its hierarchy. 

# References / License Information
## Controlled Vocabularies
[1]: [DEFC](https://vocabs.dariah.eu/defc_thesaurus/en/) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creators: Seta Štuhec, Anja Masur, Peter Andorfer, Ksenia Zaytseva, Edeltraud Aspöck]  
[2]: [PACTOLS](https://isl.ics.forth.gr/bbt-federated-thesaurus/PACTOLS/en/) (adapted) [[ODbL v1.0](https://opendatacommons.org/licenses/odbl/1-0/); Creators: Groupe PACTOLS/FRANTIQ]  
[3]: [iDAI.world](https://isl.ics.forth.gr/bbt-federated-thesaurus/DAI/en/) (adapted)[](https://vocabs.dariah.eu/defc_thesaurus/en/) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creators: Annika Kirscheneder, Camilla Colombi, Elenore Pape, Gabriele Rasbach, Henriette Senst, Lena Vitt, Matthias Block, Nina Dworschak, Reinhard Förtsch, Sabine Thänert]  
[4]: [Iron-Age-Danube](https://vocabs.dariah.eu/iad_thesaurus/en/) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creator: Seta Štuhec]  
[5]: [PARTHENOS](https://vocabs.dariah.eu/parthenos_vocabularies/en/) (adapted) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creators: PARTHENOS project]  
[6]: [OeAI](https://vocabs.dariah.eu/oeai-cp/en/) (adapted) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creator: Micheline Welte]  
[7]: [DHA Taxonomy](https://vocabs.dariah.eu/dha_taxonomy/en/) (adapted) [[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en); Creators: ACDH-OEAW Team]  
[8]: [UNESCO](https://vocabularies.unesco.org/browser/thesaurus/en/) (adapted) [[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/igo/); Creators: UNESCO]  
[9]: [TaDiRAH](https://vocabs.dariah.eu/tadirah/en/) (adapted) [[CC0](https://creativecommons.org/publicdomain/zero/1.0/); Creators: Luise Borek, Canan Hastik, Vera Khramova, Jonathan Geiger]

## Literature
[10]: Hill F, Reichart R, Korhonen A (2015) SimLex-999: Evaluating Semantic Models With (Genuine) Similarity Estimation. Computational Linguistics 41:665–695. https://doi.org/10.1162/COLI_a_00237

# Contact information
Creator: Felix Kraus
Email (subsitute accordingly): firstname.lastname (at) kit (dot) edu
