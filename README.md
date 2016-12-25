# Comparing RepSeq library preparation strategies

The repository contains immune repertoire sequencing (RepSeq) datasets produced using different library prepartion techniques. The main goal of this project is to compare various molecular methods for antigen receptor sequencing. 

General comments regarding data analysis presented here:

* Only T-cell receptor repertoires are considered.
* The datasets are stored as clonotype frequency tables and contain the following columns: read (or cDNA) count, Variable/Diversity/Joining segments in IMGT format, nucleotide and amino acid sequence of the CDR3 region.
* Each dataset should have a corresponding metadata file holding information on T-cell source, the amoung of input DNA/cDNA, sequencing platform, brief description of the protocol, TCR chain (alpha or beta) and data pre-processing pipeline. Note that an optimal pre-processing method is chosen for each technology, comparison of bioinformatic methods (V-D-J mapping, etc) is out of scope of this repository.

The generic set of samples is the following:

* PBMCs from the same donor are used, split at the RNA level and distributed across participants
* Three large (100ng RNA) and small (10ng RNA) samples are used for generating technical replicas with a given library preparation protocol

General ideas for *in silico* protocol comparison:

* Library preparation techniques are compared based on their ability to resolve V-D-J junctions in an unbiased and comprehensive way, as well as the robustness of clonotype frequency quantification. Comparison parameters are listed below.
* An example dataset and its analysis is provided in the ``examples/`` folder.

# Analysis of basic repertoire characteristics

## Cross-technology comparison

### Comparing repertoire diversity estimates

The following diversity metrics are considered:

* **Chao1 index** 

* **Shannon index**

* **Gini index**

* **Rarefaction**

### Comparing V/J segment usage

![V usage](https://raw.githubusercontent.com/RepSeq/technology-comparison/master/assets/vusage.png "Variable segment frequency profiles for different replicas and different starting amounts of RNA.")

In this section only V/J segments are considered. Allelic variants are ignored, use only major allele (``*01``) is used.

* Compare V and J frequency distributions, both weighted (by read) and unweighted (by clonotype, i.e. unique CDR3)

* Compare frequency of V-J junctions, weighted and unweighted

* Perform 2-way ANOVA test and post-hoc T-test to detect V and J segments that are missed by certain technologies

### Comparing CDR3 structure

![Spectratype](https://raw.githubusercontent.com/RepSeq/technology-comparison/master/assets/spectra.png "CDR3 length distribution of in-frame and out-of-frame clonotypes.")

* Compare the CDR3 length distribution

* Compare the number of out-of-frame V-J junctions

## Using replicas

Compare the variance of Chao1 diversity index across samples. Chao1 metric describes the diversity of naive cells using the count of singletons and doubletons and is very sensitive to these numbers. 

Compare the number of unique V-J pairs detected in one, two, etc replicas and the variance of V, J and V-J pair frequency (weighted by read) across replicas.

# Analysis of T-cell clonotype quantification

The basic idea of this benchmark is to compare the robustness of T-cell clonotype quantification and to derive a model for clonotype abundance distribution each technology. This model (hereafter called sampling model) should describe the variance of clonotype abundance (for large clonotypes) and the samling probability (for small ones) under the null hypothesis of replicate sampling.

![Scatterplot](https://raw.githubusercontent.com/RepSeq/technology-comparison/master/assets/freq1.png "Correlation of clonotype frequencies.")

* The model should describe the dependence between clonotype frequency variance ``V`` and mean clonotype frequency ``M``

* A model based on read counts and their variance (discrete one) can be applied to rare clonotypes. The probability of missing a clonotype of a given read count due to sampling stochastics can also be calculated from this model.

![Sampling model](https://raw.githubusercontent.com/RepSeq/technology-comparison/master/assets/freq2.png "Mean clonotype count and coefficient of variance.")

* Coefficients of variance ``V/M`` can be compared across technologies


