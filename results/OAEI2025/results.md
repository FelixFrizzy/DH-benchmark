# Results of the [Digital Humanities track](https://oaei.ontologymatching.org/2025/digitalhumanities/index.html) of the [OAEI 2025 campaign](https://oaei.ontologymatching.org/2025/)
OAEI 2025 is the second year for the DH track to participate. For information about the goal of this track and information about the test cases, refer to the [Readme](https://github.com/FelixFrizzy/DH-benchmark/blob/main/README.md).

# Evaluation Modalities
We used the dataset v1.0.0 (https://doi.org/10.5281/zenodo.12731588) and precision, recall and F1-score for evaluation and only evaluated equivalence relationships. If matching systems resulted in either errors or zero identified matches, we considered them as failed. Adhering the [OAEI rules](https://oaei.ontologymatching.org/doc/oaei-rules.2.html), we didn't change any settings for the matching systems. 

## Resources
- VM with 8 x 2.4 GHz cores, 16GB RAM

## Steps to Reproduce the Results
- Download the evaluation client [evaluation client](https://nightly.link/dwslab/melt/workflows/java_client_upload/master/evaluation-client.zip) as explained in the [documentation](https://dwslab.github.io/melt/matcher-evaluation/client).
- Download the 2025 (or any other MELT compatible) matchers and put them in the same folder.
- Run the command

java -jar matching-eval-client-latest.jar --systems ALIN-Seals.zip logmap-melt-oaei-2021-web-latest.tar.gz logmap-bio-melt-oaei-2021-web-latest.tar.gz logmap-kg-melt-oaei-2021-web-latest.tar.gz logmap-lite-melt-oaei-2021-web-latest.tar.gz lsmatch-2.0-web-latest.tar.gz lsmatch-multilingual-2.0-web-latest.tar.gz matcha.zip MDMapperSeals.zip tim-1.0-web-latest.tar.gz  --track http://oaei.webdatacommons.org/tdrs/ dh 2024all --results oaei2025_all_oaeidh_(date +"%Y-%m-%d_%H-%M-%S") > oaei2025_all_oaeidh_(date +"%Y-%m-%d_%H-%M-%S").log



```bash
java -jar matching-eval-client-latest.jar --systems ALIN-Seals.zip logmap-melt-oaei-2021-web-latest.tar.gz logmap-bio-melt-oaei-2021-web-latest.tar.gz logmap-kg-melt-oaei-2021-web-latest.tar.gz logmap-lite-melt-oaei-2021-web-latest.tar.gz lsmatch-2.0-web-latest.tar.gz lsmatch-multilingual-2.0-web-latest.tar.gz matcha.zip MDMapperSeals.zip tim-1.0-web-latest.tar.gz --track http://oaei.webdatacommons.org/tdrs/ dh 2024all --results oaei2025_dh
```
The raw results can be found in the `raw-results_dhtrack_2025` folder in this repo.

# Results


## Overview over the matching systems
- Running successfully
    - Agent-OM
    - LogMap Bio
    - LogMap KG
    - Logmap
    - TIM
- Running without code errors / exceptions, alignments empty
    - LSMatch
    - LSMatch-Multilingual
- Running with exceptions / error, no alignments received
    - ALIN
    - Matcha
    - MDMapper


## Precision, Recall, F1-Score
| Test Case                   |Precision|          |                |               |           |Recall    |            |           |          |F1-Score  |            |           |          |
| --------------------------- |-------- | -------- | -------------- | ------------- | --------- | -------- | ---------- | --------- | -------- | -------- | ---------- | --------- | -------- |
|                             |Agent-OM | LogMap   | LogMap Bio     | LogMap KG     | TIM       | Agent-OM | LogMap   | LogMap Bio     | LogMap KG     | TIM       |Agent-OM | LogMap   | LogMap Bio     | LogMap KG     | TIM       
| arch1_defc-pactols          | **1.00**    | 0.33     | 0.20         | 0.90         | 0.13         | 0.20         | **1.00**         | 0.20         | 0.90         | 0.60         | 0.33         | 0.50         | 0.20         | **0.90**         | 0.21
| arch2_idai-pactols          | **1.00**    | 0.35     | 0.40         | 0.40         | 0.04         | 0.12         | **1.00**         | 0.71         | 0.71         | 0.12         | 0.21         | **0.52**         | 0.51         | 0.51         | 0.06
| arch3_ironagedanube-pactols | **1.00**    | 0.31     | 0.40         | 0.40         | 0.04         | 0.20         | **0.80**         | **0.80**         | **0.80**         | 0.40         | 0.33         | 0.44         | **0.53**         | **0.53**         | 0.08
| arch4_pactols-parthenos     | **1.00**    | 0.42     | 0.71         | 0.71         | 0.18         | 0.50         | **0.92**         | 0.83         | 0.83         | 0.67         | 0.67         | 0.58         | **0.77**         | **0.77**         | 0.29
| cult1_idai-parthenos        | 0.50    | 0.70     | **1.00**         | **1.00**         | 0.00         | **0.38**         | 0.27         | 0.17         | 0.17         | 0.00         | **0.43**         | 0.39         | 0.30         | 0.30         | 0.00
| cult2_oeai-parthenos        | 0.91    | 0.51     | **1.00**         | **1.00**         | 0.00         | 0.43         | **0.89**         | 0.68         | 0.68         | 0.00         | 0.58         | 0.65         | **0.81**         | **0.81**         | 0.00
| dhcs1_dha-unesco            | **0.67**    | 0.25     | 0.50         | 0.50         | 0.02         | 0.40         | **0.90**         | 0.40         | 0.40         | 0.20         | **0.50**         | 0.39         | 0.44         | 0.44         | 0.04
| dhcs2_tadirah-unesco        | **1.00**    | 0.22     | 0.00         | 0.53         | 0.00         | 0.27         | **0.80**         | 0.00         | 0.67         | 0.00         | 0.42         | 0.35         | 0.00         | **0.59**         | 0.00
| Average over all tracks     | **0.88**    | 0.39     | 0.53         | 0.68         | 0.05         | 0.31         | **0.82**         | 0.47         | 0.64         | 0.25         | 0.43         | 0.48         | 0.45         | **0.61**         | 0.09


  

## Average (mean) over matchers

| Test Case                   |Precision  | Recall    | F1-Score |
| --------------------------- | --------  | --------- | -------- |
| arch1_defc-pactols          | 0.51      | 0.58      | 0.43     |
| arch2_idai-pactols          | 0.44      | 0.53      | 0.36     |
| arch3_ironagedanube-pactols | 0.43      | 0.60      | 0.38     |
| arch4_pactols-parthenos     | 0.61      | 0.75      | 0.61     |
| cult1_idai-parthenos        | 0.64      | 0.20      | 0.28     |
| cult2_oeai-parthenos        | 0.68      | 0.54      | 0.57     |
| dhcs1_dha-unesco            | 0.39      | 0.46      | 0.36     |
| dhcs2_tadirah-unesco        | 0.35      | 0.35      | 0.27     |
| Average over all tracks     | 0.51      | 0.50      | 0.41     |



## Runtimes
| Matcher              | total runtime (hh:mm:ss) |
|----------------------|--------------------------|
| Agent-OM             | not provided             |
| LogMap               | 00:00:14                 |
| LogMap Bio           | 00:00:17                 |
| LogMap KG            | 00:00:13                 |
| LogMap lite          | 00:24:52                 |
| LSMatch              | 00:00:17                 |
| LSMatch Multilingual | 00:00:18                 |
| TIM                  | 00:00:07                 |

## Discussion
When we examine the F1-scores averaged over all matchers, they range from 0.27 to 0.61. This indicates that while the matchers perform fairly well on some test cases, there is considerable room for improvement on others. 

When comparing the matching systems, LogMap KG has the best averaged F1-score of 0.61, similar to last year's OAEI. The two systems Agent-OM and TIM which took part for the first time could not outperform LogMap KG. 

Looking at execution times, the all are in the same range, between 13s and 18s to run the full track. The only exception is LogMap lite with over 20min but still results in an empty aligment. Agent-OM could not provide running times. 

In general, only half of the evaluated matchers, and only two matchers that are not based on LogMap, can find alignments. Most of the systems result in errors, which aligns with our findings in our OM-paper [1] where only five out of 17 systems could find alignments.  This makes it evident that still many matching systems cannot handle SKOS. On the other hand, it is notable that the two new systems participating for the first time can handle SKOS. 

# References
[1] F. Kraus, N. Blumenröhr, G. Götzelmann, T. Tonne, A. Streit, A Gold Standard Benchmark Dataset for Digital Humanities, in: OM-2024: The 19th International Workshop on Ontology Matching collocated with the 23rd International Semantic Web Conference (ISWC 2024), November 11th, Baltimore, USA.

[2] C. Caracciolo, J. Euzenat, L. Hollink, R. Ichise, A. Isaac, V. Malaisé, C. Meilicke, J. Pane, P. Shvaiko, H. Stuckenschmidt, O. Sváb-Zamazal, V. Svátek, Results of the Ontology Alignment Evaluation Initiative 2008, in: P. Shvaiko, J. Euzenat, F. Giunchiglia, H. Stuckenschmidt (Eds.), Proceedings of the 3rd International Workshop on Ontology Matching (OM-2008), volume 431 of CEUR Workshop Proceedings, CEUR-WS.org, Karlsruhe, Germany, 2008.

# Acknowledgements
The execution of this evaluation was funded by the research program “Engineering Digital Futures” of the Helmholtz Association of German Research Centers.
