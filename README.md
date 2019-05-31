[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2550379.svg)](https://doi.org/10.5281/zenodo.2550379)

# FOCUS

This repository contains the source code implementation of FOCUS and the datasets used to replicate the experimental results of our ICSE'19 paper:

_FOCUS: A Recommender System for Mining API Function Calls and Usage Patterns_

Phuong T. Nguyen, Juri Di Rocco, Davide Di Ruscio, Lina Ochoa, Thomas Degueule, Massimiliano Di Penta

A pre-print version of the paper is available [here](https://hal.archives-ouvertes.fr/hal-02023023/document).

Our paper has been awarded two badges by the ICSE 2019 Artifact Evaluation Track, namely "Artifacts Available" and "Artifacts Evaluated." This means that all the related artifacts have been properly documented, and they are consistent, complete, and reproducible. Furthermore, they include appropriate evidence to facilitate future reuse and reproduction. We also strictly
adhere to norms and standards of the research community for artifacts of this type.

<p align="center">
<img src="https://github.com/crossminer/FOCUS/blob/master/Badges.png" width="250">
</p>

A detailed instruction on how to experiment the artifacts is provided [here](https://github.com/crossminer/FOCUS/blob/master/README.pdf).


## Introduction

FOCUS is a context-aware collaborative-filtering recommendation system that exploits cross relationships among OSS projects to suggest the inclusion of additional API invocations and concrete API usage patterns. The current implementation targets Java code specifically.

Implementing a collaborative-filtering recommendation system requires to assess the similarity of two customers, i.e., two software projects. Existing approaches consider that any two projects using an API of interest are equally valuable sources of knowledge. Instead, we postulate that not all projects are equal when it comes to recommending usage patterns: a project that is highly similar to the project currently being developed should provide higher quality patterns than a highly dissimilar one.

Our collaborative-filtering recommendation system attempts to narrow down the search scope by only considering the projects that are the most similar to the active project. Therefore, methods that are typically used conjointly by similar projects in similar contexts tend to be recommended first.

We incorporate these ideas in a new context-aware collaborative filtering recommender system that mines OSS repositories to provide developers with API **F**uncti**O**n **C**alls and **US**age patterns: FOCUS. Our approach employs a new model to represent mutual relationships between projects and collaboratively mines API usage from the most similar projects.

## Repository Structure

This repository is organized as follows:

* The [tools](./tools) directory contains the implementation of the different tools we developed:
	* [Focus](./tools/Focus): The Java implementation of FOCUS
	* [FocusRascal](./tools/FocusRascal): A set of tools written in [Rascal](https://www.rascal-mpl.org/) that are used to (i) transform raw Java source and binary code into FOCUS-processable and PAM-processable data (ii) retrieve concrete Java usage patterns
	* [PAM](./tools/PAM): A set of Python scripts allowing to compare our approach to PAM
* The [dataset](./dataset) directory contains the datasets described in the paper that we use to evaluate FOCUS:
	* [jars](./dataset/jars): 3,600 JAR files extracted from Maven Central (the raw MV<sub>L</sub> dataset)
	* [MV_L](./dataset/MV_L): meta-data of the MV<sub>L</sub> dataset (extracted from 3,600 JAR files)
	* [MV_S](./dataset/MV_S): meta-data of the MV<sub>S</sub> dataset (extracted from 1,600 JAR files)
	* [SH_L](./dataset/SH_L): meta-data of the SH<sub>L</sub> dataset (extracted from the source code of 610 GitHub projects)
	* [SH_S](./dataset/SH_S): meta-data of the SH<sub>S</sub> dataset (extracted from the source code of 200 GitHub projects)

__Note<sup>1</sup>__: the archive of 5,147 Java projects retrieved from GitHub via the [Software Heritage](https://www.softwareheritage.org/) archive is available at [this url](https://annex.softwareheritage.org/public/dataset/vault-crossminer/856749_done_with_origins.txt.gz).

__Note<sup>2</sup>__: The results presented in the paper can be reproduced following the instructions contained in the [Focus](./tools/Focus) directory.


## How to cite
If you find our work useful for your research, please cite the paper using the following BibTex entry:

```
@INPROCEEDINGS{NDDLDD2019, 
author={P.T. {Nguyen} and J. {Di Rocco} and D. {Di Ruscio} and L. {Ochoa} and T. {Degueule} and M. {Di Penta}}, 
booktitle={2019 IEEE/ACM 41st International Conference on Software Engineering (ICSE)}, 
title={FOCUS: A Recommender System for Mining API Function Calls and Usage Patterns}, 
year={2019}, 
volume={}, 
number={}, 
doi={10.1109/ICSE.2019.00109}, 
month={May},}

```

