# Analysis of T-cell clonotype quantification

The basic idea of this benchmark is to compare the robustness of T-cell clonotype quantification and to derive a model for clonotype abundance distribution each technology. This model (hereafter called sampling model) should describe the variance of clonotype abundance (for large clonotypes) and the samling probability (for small ones) under the null hypothesis of replicate sampling.

* The model should describe the dependence between clonotype frequency variance ``V`` and mean clonotype frequency ``M``
* A model based on read counts and their variance (discrete one) can be applied to rare clonotypes. The probability of missing a clonotype of a given read count due to sampling stochastics can also be calculated from this model.
* Coefficients of variance ``V/M`` can be compared across technologies