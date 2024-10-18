This folder contains the results of the [Digital Humanities](https://oaei.ontologymatching.org/2024/digitalhumanities/index.html) of the [OAEI 2024 campaign](https://oaei.ontologymatching.org/2024/). 

## Resources
- VM with 8 x 2.4 GHz cores, 16GB RAM

## Steps to reproduce results
- Download the evaluation client [evaluation client](https://nightly.link/dwslab/melt/workflows/java_client_upload/master/evaluation-client.zip) as explained in the [documentation](https://dwslab.github.io/melt/matcher-evaluation/client).
- Download the 2024 (or any other MELT compatible) matchers and put them in the same folder.
- Run the command
```bash
java -jar matching-eval-client-latest.jar --systems logmap-melt-oaei-2021-web-latest.tar.gz logmap-bio-melt-oaei-2021-web-latest.tar.gz logmap-kg-melt-oaei-2021-web-latest.tar.gz logmap-lite-melt-oaei-2021-web-latest.tar.gz matcha.tar.gz "ALIN - Jomar Silva.zip" MDMapper-seals.zip https://match.tomato.irit.fr/match --track http://oaei.webdatacommons.org/tdrs/ dh 2024all --results oaei2024_dh
```
The raw results can be found in the `raw-results_dhtrack_2024` folder in this repo.

# Results


## Overview over the matching systems
- Running successfully
    - Matcha
    - LogMap Bio
    - LogMap KG
    - Logmap
- Running without code errors / exceptions, alignments empty
    - TOMATO
    - LogMap lite
- Running with exceptions / error, no alignments received
    - ALIN
    - MDMapper
    - OntoMatch (standalone, not possible to run with MELT / SEALS)

## Recall, Precision, F1-Score
(table)


## Runtimes
(table)

## Discussion
When we examine the average F1-scores across all matchers, they range from 0.33 to 0.76. This indicates that while the matchers perform fairly well on some test cases, there is considerable room for improvement on others. Notably, PARTHENOS appears in both the test case with the highest F1-score (oeai-parthenos) and the one with the lowest F1-score (idai-parthenos). This can be explained by the fact that the paired CVs differ in language: _iDAI_ almost only includes German terms, _PARTHENOS_ only English and OeAI German and English. This suggests that most matching systems focus on English ontologies and struggle to deal with other languages. It also indicates that the systems are more sensitive to language differences than to the actual domain of the terms.

When comparing the matching systems, LogMap has the best averaged F1-score of 0.60, but the other systems with 0.53 are not far off.

Looking at execution times, the all are in the same range, between 13s and 21s to run the full track. The only exception is LogMap lite with over 20min but still results in an empty aligment.

In general, less than half of the evaluated matchers, and only one matcher that is not based on LogMap, can find alignments. Most of the systems result in errors, which aligns with our findings in our OM-paper [1] where only five out of 17 systems could find alignments.  This makes it evident that a majority of matching systems cannot handle SKOS even though SKOS is widely used in research across different fields. This issue was already noted in the early library tracks [2] but has yet to be addressed. 

# References
[1] (accepted, not yet published) F. Kraus, N. Blumenröhr, G. Götzelmann, T. Tonne, A. Streit, A Gold Standard Benchmark Dataset for Digital Humanities, in: OM-2024: The 19th International Workshop on Ontology Matching collocated with the 23rd International Semantic Web Conference (ISWC 2024), November 11th, Baltimore, USA.
[2] C. Caracciolo, J. Euzenat, L. Hollink, R. Ichise, A. Isaac, V. Malaisé, C. Meilicke, J. Pane, P. Shvaiko, H. Stuckenschmidt, O. Sváb-Zamazal, V. Svátek, Results of the Ontology Alignment Evaluation Initiative 2008, in: P. Shvaiko, J. Euzenat, F. Giunchiglia, H. Stuckenschmidt (Eds.), Proceedings of the 3rd International Workshop on Ontology Matching (OM-2008), volume 431 of CEUR Workshop Proceedings, CEUR-WS.org, Karlsruhe, Germany, 2008.

# Acknowledgement
The execution of this evaluation was funded by the research program “Engineering Digital Futures” of the Helmholtz Association of German Research Centers.