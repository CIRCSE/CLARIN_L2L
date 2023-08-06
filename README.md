# CLARIN L2L

* [introduction](#introduction)
* [content structure](#structure)

## Introduction

In this repository, we publish the code, data and documentation produced for the project "L2L - From Lemmatizers to Linkers". The project was financed within the program [CLARIN Resource Families Project Funding](https://www.clarin.eu/content/clarin-resource-families-project-funding).

The aim of the project was to explore the possibility of using an approach based on the LOD paradigm and lemmatization to achive interoperability between the lexical and textual resources that are avaiable within the [CLARIN](https://www.clarin.eu/) infrastructure. The idea is to use unique identifier to lemmas to: 1. index the entries in lexical resources 2. link lemmatized resource to them 3. link the automatically lemmatized resources too. This is the same approach pioneered by the [Lila - Linking Latin](https://lila-erc.eu/) project (see [Passarotti et al. 2020]([https://doi.org/10.4454/ssl.v58i1.277])).

In the course of the project, we created a prototype service that: a) scans the CLARIN Virtual Language Observatoiry ([VLO](https://vlo.clarin.eu/)); b) collects all textual resources available in a given language and distributed in a series of format that the tool is able to parse (CSV, txt, XML); c) tokenizes and lemmatizes them, using the appropriate models in [UDPipe 2](https://ufal.mff.cuni.cz/udpipe); d) creates a relational database that contains an index of texts and lemmas and a frequency table of each lemma in the textual resources; e) provides a frontend to visualize the results.

The tool is language independent (as any language can be used as input), but a demo is available only for Italian. A dump of the DB created with a subset of the textual resources used for the demo is available in the `data` folder.

## Structure

The materials are divided in the following directories and subdirectories:
- `data` contains:
    - a dump of the DB used by the demo of our tool
    - a directory with 3 RDF files generated from the DB using [this code](code/notebooks/clarindb2lod.ipynb), namely: 1. the lemma bank, 2. the frequency lists, 3. a link to a [sentiment lexicon](http://hdl.handle.net/20.500.11752/ILC-73) of Italian.
- `code` contains:
    - Jupyter notebooks used to generate the RDF data and explore them
    - the source code of our demo tool (COMING SOON)
- `doc` contains the documentation for this project, including:
    - a survey of lexical and textual resources usable as sources of data
    - a markdown file containing a detailed overview of our demo