# Results of the [Digital Humanities track](https://oaei.ontologymatching.org/2024/digitalhumanities/index.html) of the [OAEI 2024 campaign](https://oaei.ontologymatching.org/2024/)
OAEI 2024 is the first year for the DH track to participate. For information about the goal of this track and information about the test cases, refer to the [Readme](https://github.com/FelixFrizzy/DH-benchmark/blob/main/README.md).

# Evaluation Modalities
We used precision, recall and F1-score for evaluation and only evaluated equivalence relationships. If matching systems resulted in either errors or zero identified matches, we considered them as failed. Adhering the [OAEI rules](https://oaei.ontologymatching.org/doc/oaei-rules.2.html), we didn't change any settings for the matching systems. 

## Resources
- VM with 8 x 2.4 GHz cores, 16GB RAM

## Steps to Reproduce the Results
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
## Precision, Recall, F1-Score
| Test Case                   |Precision |                |               |           |Recall    |            |           |          |F1-Score  |            |           |          |
| --------------------------- | -------- | -------------- | ------------- | --------- | -------- | ---------- | --------- | -------- | -------- | ---------- | --------- | -------- |
|                             | LogMap   | LogMap Bio     | LogMap KG     | Matcha    | LogMap   | LogMap Bio | LogMap KG | Matcha   | LogMap   | LogMap Bio | LogMap KG | Matcha   |
| arch1_defc-pactols          | 0.33     | 0.20           | 0.90          | **1.00**  | **1.00** | 0.20       | 0.90      | 0.90     | 0.50     | 0.20       | 0.90      | **0.95** |
| arch2_idai-pactols          | 0.35     | **0.40**       | **0.40**      | 0.31      | **1.00** | 0.71       | 0.71      | 0.24     | **0.52** | 0.51       | 0.51      | 0.27     |
| arch3_ironagedanube-pactols | 0.31     | 0.40           | 0.40          | **0.67**  | **0.80** | **0.80**   | **0.80**  | **0.80** | 0.44     | 0.53       | 0.53      | **0.73** |
| arch4_pactols-parthenos     | 0.42     | 0.71           | 0.71          | **0.83**  | **0.92** | 0.83       | 0.83      | 0.83     | 0.58     | 0.77       | 0.77      | **0.83** |
| cult1_idai-parthenos        | 0.70     | **1.00**       | **1.00**      | 0.00      | **0.27** | 0.17       | 0.17      | 0.00     | **0.39** | 0.30       | 0.30      | 0.00     |
| cult2_oeai-parthenos        | 0.51     | **1.00**       | **1.00**      | 0.90      | **0.89** | 0.68       | 0.68      | 0.74     | 0.65     | **0.81**   | **0.81**  | **0.81** |
| dhcs1_dha-unesco            | 0.25     | **0.50**       | **0.50**      | 0.08      | **0.90** | 0.40       | 0.40      | 0.60     | 0.39     | **0.44**   | **0.44**  | 0.14     |
| dhcs2_tadirah-unesco        | 0.48     | **0.53**       | 0.22          | 0.00      | 0.67     | 0.67       | **0.80**  | 0.00     | 0.56     | **0.59**   | 0.35      | 0.00     |
| Average over all tracks     | 0.42     | 0.59           | **0.64**      | 0.49      | **0.81** | 0.56       | 0.66      | 0.58     | 0.50     | 0.52       | **0.58**      | 0.53 |

## Average (mean) over matchers

| Test Case                   |Precision | Recall    | F1-Score |
| --------------------------- | -------- | --------- | -------- |
| arch1_defc-pactols          | 0.61     | 0.75      | 0.64     |
| arch2_idai-pactols          | 0.44     | 0.80      | 0.56     |
| arch3_ironagedanube-pactols | 0.88     | 0.36      | 0.45     |
| arch4_pactols-parthenos     | 0.33     | 0.58      | 0.36     |
| cult1_idai-parthenos        | 0.46     | 0.65      | 0.53     |
| cult2_oeai-parthenos        | 0.85     | 0.75      | 0.77     |
| dhcs1_dha-unesco            | 0.36     | 0.66      | 0.45     |
| dhcs2_tadirah-unesco        | 0.31     | 0.53      | 0.37     |
| Average over all tracks     | 0.53     | 0.63      | 0.52     |


## Runtimes
| Matcher     | total runtime (hh:mm:ss) |
|-------------|--------------------------|
| LogMap      | 00:00:13                 |
| LogMap Bio  | 00:00:15                 |
| LogMap KG   | 00:00:11                 |
| LogMap lite | 00:22:16                 |
| Matcha      | 00:00:15                 |
| TOMATO      | 00:00:21                 |

## Discussion
When we examine the F1-scores averaged over all matchers, they range from 0.33 to 0.76. This indicates that while the matchers perform fairly well on some test cases, there is considerable room for improvement on others. 

When comparing the matching systems, LogMap has the best averaged F1-score of 0.60, but the other systems with 0.53 are not far off.

Looking at execution times, the all are in the same range, between 13s and 21s to run the full track. The only exception is LogMap lite with over 20min but still results in an empty aligment.

In general, less than half of the evaluated matchers, and only one matcher that is not based on LogMap, can find alignments. Most of the systems result in errors, which aligns with our findings in our OM-paper [1] where only five out of 17 systems could find alignments.  This makes it evident that a majority of matching systems cannot handle SKOS even though SKOS is widely used in research across different fields. This issue was already noted in the early library tracks [2] but has yet to be addressed. 

# References
[1] (accepted, not yet published) F. Kraus, N. Blumenröhr, G. Götzelmann, T. Tonne, A. Streit, A Gold Standard Benchmark Dataset for Digital Humanities, in: OM-2024: The 19th International Workshop on Ontology Matching collocated with the 23rd International Semantic Web Conference (ISWC 2024), November 11th, Baltimore, USA.
[2] C. Caracciolo, J. Euzenat, L. Hollink, R. Ichise, A. Isaac, V. Malaisé, C. Meilicke, J. Pane, P. Shvaiko, H. Stuckenschmidt, O. Sváb-Zamazal, V. Svátek, Results of the Ontology Alignment Evaluation Initiative 2008, in: P. Shvaiko, J. Euzenat, F. Giunchiglia, H. Stuckenschmidt (Eds.), Proceedings of the 3rd International Workshop on Ontology Matching (OM-2008), volume 431 of CEUR Workshop Proceedings, CEUR-WS.org, Karlsruhe, Germany, 2008.

# Acknowledgement
The execution of this evaluation was funded by the research program “Engineering Digital Futures” of the Helmholtz Association of German Research Centers.## Raw Alignments
Download [here](#TODO link)
