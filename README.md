# Alkyne_Semihydrogenation

This repository contains a Jupyter notebook inspired/based on work and analyses done in:

* S. K. Kariofillis, A. G. Doyle *et al.*, *J. Am. Chem. Soc.* **2022**, *144*, 1045-1055. (https://pubs.acs.org/doi/10.1021/jacs.1c12203)
* https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html (last accessed 10.08.22)
* talktorial from the Volkamer lab: https://projects.volkamerlab.org/teachopencadd/talktorials/T006_compound_maximum_common_substructures.html (last accessed 10.08.22)
* S. H. Newman-Stonebraker, A. G. Doyle *et al.*, *Science* **2021**, *374*, 301-308. Zenodo (2021); http://doi.org/10.5281/zenodo.5227162 Jupyter notebook available under: https://github.com/SigmanGroup/Threshold  
* J. Dotson, M. Sigman *et al.*, *J. Am. Chem. Soc.* **2023**, *145, 1*, 110-121. Jupyter notebook available under: https://github.com/SigmanGroup/Multiobjective_Optimization

## Requirements
* python 3 (tested on 3.9.7)
* numpy (1.20.3)
* pandas (1.4.1)
* xlrd (2.0.1)
* rdkit (2021.09.04)
* matplotlib (3.5.0)
* seaborn (0.11.1)
* scikit-learn (1.0.2)
* umap-learn (0.5.2)
* scipy (1.7.3)

## Chemical Space Mapping
The first part of the notebook is designed to work with 4 excel spreadsheets:
1) DataSet_InternalAlkynes.xlsx
2) DataSet_TerminalAlkynes.xlsx
3) DataSet_Substrates.xlsx
4) DataSet_LiteratureSubstrates.xlsx

The first two excel files contain calculated physicochemical descriptors for commercially available internal and terminal alkynes, respectively. The third spreadsheet contains catalytic output parameters of 31 tested substrates. The fourth spreadsheet contains reported yields for alkyne semihydrogenation reaction using molecular hydrogen.

* The chemical space of commerically available alkynes is mapped using the first two spreadsheets. 
Dimension reduction is performed using PCA or UMAP, followed by hierarchical clustering using the Ward's method. The preferential reduced representation and optimal amount of clusters is determined by silhouette score analysis and comparing the silhouette shapes.
* Each tested substrate is plotted on the generated chemical space map
* The semihydrogenation rates of each substrate is plotted on the generated chemical space map
* The literature reported yield and number of reports of alkyne semihydrogenation reactions is plotted on the generated chemical space map
* The **n** central molecules of each cluster are depicted
* The maximum common substructure (MCS) of each cluster is depicted
* The diversity of the clustering workflow is analyzed via random sampling

## Threshold Analysis and Logistic Regression
The second part of the notebook works with two excel spreadsheets:

1) DataSet_AllAlkynes_TMS.xlsx
2) DataSet_Tested.xlsx

These spreadsheets are condensed forms of the spreadsheets used in the first part of the notebook.

* Search for best one-parameter thresholds to separate alkynes into "easy" and "difficult" to hydrogenate according to their semihydrogenation rates.
* Search for best one- and two-parameter logistic regression models, including virtual screening

This part makes use of two .py scripts from https://github.com/SigmanGroup/Multiobjective_Optimization found in src/:
* Logistic_Regression.py
* logreg_stats

## Contributors
The Jupyter notebook has been built by Jordan De Jesus Silva and is based on aforementioned work.
