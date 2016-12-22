## Note on samples

The folder contains clonotype tables obtained for a unified T-cell repertoire sample.

Naming convention is the following: ``${sample id}_${ng of input RNA}_${TCR chain}.txt.gz``.

Here ``${sample id}`` is the identifier of an independent sample split at the level RNA extracted from sorted T-cells.

The quantity of input RNA was determined experimentally, and is somewhat different from the expected 10/100ng.

For example, ``A2_8_beta.txt.gz`` means TCR beta sequencing performed for sample ``A2`` that is 10ng RNA.

Files a compressed using gzip.

## Note on data pre-processing

De-multiplexing, unique molecular identifier (UMI) extraction and UMI-based consensus assembly was performed using MIGEC software. A threshold of 12 and 6 reads per UMI was used for 8 and 65 ng samples respectively. V-D-J mapping and CDR3 extraction was performed using MIXCR software with default settings.

Creadit for data pre-processing goes to Alexey Davidov.
