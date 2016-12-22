# Analysis of basic repertoire characteristics

## Cross-technology comparison

### Comparing diversity

Chao1 index

Shannon index

Gini index

Rarefaction curve

### Comparing V/J segment usage

Only segments, ignore alleles, use only major allele (``*01``)

Compare V and J frequency distributions, both weighted (by read) and unweighted (by clonotype, i.e. unique CDR3)

Compare frequency of V-J junctions, weighted and unweighted

Perform 2-way ANOVA test and post-hoc T-test to detect V and J segments that are missed by certain technologies

### Comparing CDR3 structure

Compare the CDR3 length distribution

Compare the number of out-of-frame V-J junctions

## Using replicas

Compare the variance of Chao1 diversity index across samples. Chao1 metric describes the diversity of naive cells using the count of singletons and doubletons and is very sensitive to these numbers. 

Number of V-J pairs detected in one, two, etc replicas. Variance of V, J and V-J pair frequency (weighted by read) across replicas

