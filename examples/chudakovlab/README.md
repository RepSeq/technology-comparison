## Dataset origin

The folder contains clonotype tables obtained for replicas of an unified T-cell repertoire sample.

Naming convention is the following: ``${replica id}_${ng of input RNA}_${TCR chain}.txt.gz``. Here ``${replica id}`` is the identifier of independent replicas split at the level RNA extracted from sorted T-cells. For example, ``A2_8_beta.txt.gz`` means TCR beta sequencing performed for ``A2`` replica that contains 8ng RNA.

> **NOTE** The quantity of input RNA was determined experimentally, and is somewhat different from the expected 10/100ng. Files a compressed using gzip.

## Data pre-processing

De-multiplexing, unique molecular identifier (UMI) extraction and UMI-based consensus assembly was performed using [MIGEC](https://github.com/mikessh/migec) software. A threshold of 12 and 6 reads per UMI was used for 8 and 65 ng samples respectively. V-D-J mapping and CDR3 extraction was performed using [MIXCR](https://github.com/milaboratory/mixcr) software with default settings.

> Credit for data pre-processing goes to Alexey Davidov.
