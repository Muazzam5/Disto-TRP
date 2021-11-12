# Disto-TRP 
# An approach for identifying transient receptor potential (TRP) channels using structural information generated by AlphaFold

## Introduction
In this study we proposed a method named as Disto-TRP, that utilized the structural information obtained from AlphaFold to effectively identifying Transient Receptor Potential (TRP) channels.

The structure of TRP channel composed of six transmembrane domain (S1-S6). The pore loop exist between S5 and S6, that allows the movement of ion particles such as Ca2+, Mg2+, and Na+ across the plasma membrane. It is also noteworthy that the N-Terminal and C-Terminal of the TRP channels exist in the cytosol. The below Figure 1 shows the architecture of the TRP channels.

## Fig.1. A typical depiction of TRP channel's structure.
![](images/TRP_Structure.png)

Understanding the structure of protein is quite important since it assist to understand the function of proteins. Prediction of protein structure is a challenging task from many decades. Recently, the DeepMind released the latest version of AlphaFold [1] that attempts to predict the structure of proteins. 

A Distogram is a distance matrix that contains information about the distance between the pairs of amino acids. AlphaFold generates this distogram based on the represntations of the target protein sequence and the features of the corresponding muliple sequence alighment (MSA). We used Distogram as novel feature set to develop our method.

## Methodology
In our current study we used two databases for collecting data, including Transporters Classification database (TCDB) and The Universal Protein Resource (UniProt) database. Thus, we collected tranient receptor potential (TRP) channels and other (non-TRP) channel porteins from the above mentioned data sources.

After acquiring the distorgram for TRP and non-TRP channels, we transformed the distograms into features. Furthermore, we combined the Distogram features with the features from various BERT [2] models to construct a hybrid feature set and utilized the resultant composite feature set as input to the Support Vector Machine (SVM) Classifier to classify TRP channels from general channel proteins.

## Fig.2. An illustration of the entire framework of the proposed study
![](images/Disto_trp.png)


## Comparison of our method with exisiting techniques
We compared our method with different feature generation methods:
* Amino Acid Composition (AAC)
* Dipeptide Composition (DPC)
* Position Specific Scoring Matrices (PSSM)

We also compared our method with using various classifiers:
* Extra Trees Classifier (EXT)
* Random Forest Classifier (RFC)
* Support Vector Machine (SVM)

We also compared our method with our previous study:
* TRP-BERT [3]
* Disto-TRP (current study)

We further assessed the performance of our method with composite features of Distogram with domain specific BERT models:
* BioBERT [4]
* TAPE (Tasks Assessing Protein Embeddings) BERT [5]

## References
1. J. Jumper et al., "Highly accurate protein structure prediction with AlphaFold," Nature, vol. 596, no. 7873, pp. 583-589, 2021.
1. J. D. M.-W. C. Kenton and L. K. Toutanova, "Bert: Pre-training of deep bidirectional transformers for language understanding," in NAACL HLT 2019 - 2019 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies - Proceedings of the Conference, 2019, pp. 4171-4186.
1. S. M. A. Shah and Y.-Y. Ou, "TRP-BERT: Discrimination of transient receptor potential (TRP) channels using contextual representations from deep bidirectional transformer based on BERT," Computers in Biology and Medicine, p. 104821, 2021.
1.	J. Lee et al., "BioBERT: a pre-trained biomedical language representation model for biomedical text mining," Bioinformatics, vol. 36, no. 4, pp. 1234-1240, 2020.
1.	R. Rao et al., "Evaluating protein transfer learning with TAPE," Advances in neural information processing systems, vol. 32, p. 9689, 2019.




