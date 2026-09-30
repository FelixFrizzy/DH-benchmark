# Results of the [Digital Humanities track](https://oaei.ontologymatching.org/2026/digitalhumanities/index.html) of the [OAEI 2026 campaign](https://oaei.ontologymatching.org/2026/)
OAEI 2026 is the second year for the DH track to participate. For information about the goal of this track and information about the test cases, refer to the [Readme](https://github.com/FelixFrizzy/DH-benchmark/blob/main/README.md).

# Evaluation Modalities
We used the dataset v1.1.0 (https://doi.org/10.5281/zenodo.12731588) and precision, recall and F1-score for evaluation and only evaluated equivalence relationships. If matching systems resulted in either errors or zero identified matches, we considered them as failed. Adhering the [OAEI rules](https://oaei.ontologymatching.org/doc/oaei-rules.2.html), we didn't change any settings for the matching systems. 

## Resources
- VM with 8 x 2.4 GHz cores, 16GB RAM

## Steps to Reproduce the Results
- Download the [evaluation client](https://nightly.link/dwslab/melt/workflows/java_client_upload/master/evaluation-client.zip) as explained in the [documentation](https://dwslab.github.io/melt/matcher-evaluation/client).
- Download the 2026 (or any MELT‑compatible) matchers and put them in the same folder.


- Run the command
```bash
java -jar matching-eval-client-latest.jar \
  --systems \
  ../Matcher/2026/ALIN-2026.zip \
  ../Matcher/2026/CHARM-2026.zip \
  ../Matcher/2026/drama-2026.tar.gz \
  ../Matcher/2026/logmap-2026.tar.gz \
  ../Matcher/2026/logmap-bio-2026.tar.gz \
  ../Matcher/2026/logmap-kg-2026.tar.gz \
  ../Matcher/2026/logmap-lite-2026.tar.gz \
  ../Matcher/2026/lsmatch-2026.tar.gz \
  ../Matcher/2026/lsmatch-multilingual-2026.tar.gz \
  ../Matcher/2026/matcha-2026.tar.gz \
  ../Matcher/2026/relmap-2026.tar.gz \
  ../Matcher/2026/secea-2026.tar.gz \
  ../Matcher/2026/tim-2026.tar.gz \
  --track http://oaei.webdatacommons.org/tdrs/ dh 2024all \
  --results oaei2026_dh
```
The raw results can be found in the `raw-results_dhtrack_2026` folder in this repo.

# Results


## Overview over the matching systems
- Running successfully
    - LogMap KG
    - Matcha
    - MOSAIC*
    - SECEA
    - TIM
- Running without code errors / exceptions, alignments empty
    - LogMap
    - LogMap Bio
    - LogMap lite
    - LSMatch
    - LSMatch-Multilingual
- Running with exceptions / error, no alignments received
    - ALIN
    - CHARM
    - DRAMA
    - RelMap

*: These results were provided by the system authors and could not be verified by executing the system using MELT.




## Precision, Recall, F1-Score

| Test Case | Precision |  |  |  |  | Recall |  |  |  |  | F1-Score |  |  |  |  |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
|  | LogMap KG | Matcha | MOSAIC | SECEA | TIM | LogMap KG | Matcha | MOSAIC | SECEA | TIM | LogMap KG | Matcha | MOSAIC | SECEA | TIM |
| arch1_defc-pactols | 0.90 | **1.00** | 0.78 | 0.13 | 0.50 | **0.90** | **0.90** | 0.70 | 0.70 | 0.80 | 0.90 | **0.95** | 0.74 | 0.22 | 0.62 |
| arch2_idai-pactols | 0.39 | 0.19 | **0.60** | 0.06 | 0.20 | 0.71 | **0.76** | 0.18 | 0.24 | 0.18 | **0.50** | 0.30 | 0.27 | 0.10 | 0.19 |
| arch3_ironagedanube-pactols | 0.40 | **0.67** | **0.67** | 0.10 | 0.24 | **0.80** | **0.80** | **0.80** | **0.80** | **0.80** | 0.53 | **0.73** | **0.73** | 0.18 | 0.36 |
| arch4_pactols-parthenos | 0.71 | 0.83 | **1.00** | 0.25 | 0.58 | **0.83** | **0.83** | 0.58 | 0.75 | 0.58 | 0.77 | **0.83** | 0.74 | 0.38 | 0.58 |
| cult1_idai-parthenos | **1.00** | 0.34 | 0.00* | 0.22 | 0.58 | 0.17 | **0.46** | 0.00* | 0.10 | 0.13 | 0.30 | **0.39** | 0.00* | 0.13 | 0.22 |
| cult2_oeai-parthenos | **1.00** | 0.90 | 0.68 | 0.57 | 0.75 | 0.68 | **0.74** | 0.64 | 0.62 | 0.51 | **0.81** | **0.81** | 0.66 | 0.59 | 0.61 |
| dhcs1_dha-unesco | **0.50** | 0.08 | 0.36 | 0.04 | 0.12 | 0.40 | **0.60** | 0.40 | 0.50 | 0.20 | **0.44** | 0.14 | 0.38 | 0.08 | 0.15 |
| dhcs2_tadirah-unesco | 0.53 | 0.50 | **0.69** | 0.08 | 0.00* | **0.67** | **0.67** | 0.60 | 0.47 | 0.00* | 0.59 | 0.57 | **0.64** | 0.14 | 0.00* |
| Average over all tracks | **0.68** | 0.56 | 0.60 | 0.18 | 0.37 | 0.64 | **0.72** | 0.49 | 0.52 | 0.40 | **0.61** | 0.59 | 0.52 | 0.23 | 0.34 |

## Average (mean) over matchers

| Test Case | Precision | Recall | F1-Score |
| --- | ---: | ---: | ---: |
| arch1_defc-pactols | 0.66 | 0.80 | 0.68 |
| arch2_idai-pactols | 0.29 | 0.41 | 0.27 |
| arch3_ironagedanube-pactols | 0.41 | 0.80 | 0.51 |
| arch4_pactols-parthenos | 0.68 | 0.72 | 0.66 |
| cult1_idai-parthenos | 0.43 | 0.17 | 0.21 |
| cult2_oeai-parthenos | 0.78 | 0.64 | 0.70 |
| dhcs1_dha-unesco | 0.22 | 0.42 | 0.24 |
| dhcs2_tadirah-unesco | 0.36 | 0.48 | 0.39 |
| Average over all tracks | 0.48 | 0.55 | 0.46 |

## Runtimes

| Matcher | Total runtime (hh:mm:ss) |
| --- | ---: |
| LogMap KG | 00:00:16 |
| Matcha | 00:05:34 |
| MOSAIC | - |
| SECEA | 00:00:05 |
| TIM | 00:00:09 |

\* These test cases were not successful (TIM on `tadirah-unesco`) or were not provided (MOSAIC on `idai-parthenos`) and are treated as zero when calculating averages. 

## Discussion
When comparing systems, LogMap KG has the best average F1-score of 0.61, closely followed by Matcha. TIM improved considerably compared to last year and now reaches an average F1-score of 0.34.

The two newcomers, SECEA and MOSAIC, were also successful in finding alignments. It is notable that both systems can handle SKOS in their first year participating in this track.

On the downside, LogMap and LogMap Bio, which were successful in past years, did not find any instance alignments this year. LogMap KG was the only successful LogMap variant. Several other systems returned empty alignments or resulted in errors, showing that handling SKOS remains a problem for many matching systems.

Looking at execution times, the successful systems need between 5 and 16 seconds for the full track, except Matcha, which needs 5 minutes and 34 seconds. MOSAIC did not provide runtimes. When trading off results and speed, LogMap KG remains the best option.

# References
[1] F. Kraus, N. Blumenröhr, G. Götzelmann, T. Tonne, A. Streit, A Gold Standard Benchmark Dataset for Digital Humanities, in: OM-2024: The 19th International Workshop on Ontology Matching collocated with the 23rd International Semantic Web Conference (ISWC 2024), November 11th, Baltimore, USA.

[2] C. Caracciolo, J. Euzenat, L. Hollink, R. Ichise, A. Isaac, V. Malaisé, C. Meilicke, J. Pane, P. Shvaiko, H. Stuckenschmidt, O. Sváb-Zamazal, V. Svátek, Results of the Ontology Alignment Evaluation Initiative 2008, in: P. Shvaiko, J. Euzenat, F. Giunchiglia, H. Stuckenschmidt (Eds.), Proceedings of the 3rd International Workshop on Ontology Matching (OM-2008), volume 431 of CEUR Workshop Proceedings, CEUR-WS.org, Karlsruhe, Germany, 2008.

# Acknowledgements
The execution of this evaluation was funded by the research program “Engineering Digital Futures” of the Helmholtz Association of German Research Centers.
