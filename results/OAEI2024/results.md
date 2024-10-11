This folder contains the results of the [Digital Humanities](https://oaei.ontologymatching.org/2024/digitalhumanities/index.html) of the [OAEI 2024 campaign](https://oaei.ontologymatching.org/2024/). 

## Resources
- 3,6 GHz 8-Core Intel i9, 32GB RAM
- Docker resources limited to 15,8GB RAM

## Steps to reproduce results
- Download the evaluation client [evaluation client](https://nightly.link/dwslab/melt/workflows/java_client_upload/master/evaluation-client.zip) as explained in the [documentation](https://dwslab.github.io/melt/matcher-evaluation/client).
- Download the 2024 (or any other MELT compatible) matchers 
- Run the command
```
java -jar matching-eval-client-latest.jar --systems logmap-melt-oaei-2021-web-latest.tar.gz logmap-bio-melt-oaei-2021-web-latest.tar.gz logmap-kg-melt-oaei-2021-web-latest.tar.gz logmap-lite-melt-oaei-2021-web-latest.tar.gz matcha.tar.gz "ALIN - Jomar Silva.zip" MDMapper-seals.zip https://match.tomato.irit.fr/match --track http://oaei.webdatacommons.org/tdrs/ dh 2024all --results oaei2024_dh
```
