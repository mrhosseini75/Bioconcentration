# Bioconcentration

# __Introduction__
The aim of the project is to assess how chemicals are distributed within the body, in particular whether or not they are mainly concentrated within lipid tissues, whether there are additional storage sites, such as protein sites, or whether the substance is metabolised or eliminated.
To do this, it is necessary to know the bioconcentration of each available substance, which reflects the increase in chemical agents through the skin and respiratory surfaces.
To quantify this phenomenon, many regulatory frameworks use the Bioconcentration Factor (BCF), which is a proportionality constant derived from comparing the concentration of the substance in a given organism with that found in water at steady state.
Depending on the BCF value, the various chemicals are divided into three classes:
Inert substances: compounds concentrated primarily within lipid tissues (class 1) 
Specifically bioconcentrated substances: concentrates not only within lipid tissues but also within other tissues (class 2) 
Substances with low bioconcentration: Substances with low BCF due to their rapid elimination by the body (class 3) [1]
The intention is to proceed, initially by making a visualization of the available data by means of PCA, and then to evaluate which are the most important characteristics of the molecule that allow to discriminate its belonging to a certain class, thanks to the LDA, which will be performed for each pair of classes.
Subsequently, the following classifiers are implemented: MLN, SVM (both linear and non-linear), Bayesian Naive, NN.
The aim is to create different algorithms which, having input data on chemical substances, make a decision regarding the belonging of each of the three classes, and then evaluate which of these algorithms is the most effective in processing the available data.

# __Dataset__
The dataset is a table, where each row corresponds to one of the 779 chemicals used to determine the bioconcentration mechanisms.
The first two columns represent substance identifiers, i.e. the CAS number, and their SMILES representation.
Of the substances analysed, as can be seen in the third column, only 25% are included in the test set, while the remaining 75% are included in the training set.
The next nine columns represent the values of some molecular descriptors, and therefore containing numbers, which in our data analysis will be the independent variables, and according to their value the various classification algorithms will decide for each sample whether it belongs to a certain class.
In particular, the nine variables available indicate:
nHM: number of heavy atoms
piPC09: counting the paths of length 9 of the hydrogen-suppressed molecular graph
PCD: represents path count based on graph theory, and increases as multiple bonds increase.
X2Av: average connectivity index of order 2
MlogP: it represents the Kow, that is the partition coefficient of n-octanol-water calculated through the Moriguchi's model
ON1V: is the modified Zagreb mean index of the first order
N-072: is the count of the presence in the molecule of RCO-N<, RCS-N, and >NCX=X, where X corresponds to any very electronegative atom.
B02[C-N]: it is worth 1 if there is at least one pair of C and N atoms separated by at least two bonds, otherwise it is worth 0
F04[C-O]: is the count of bound C and O atoms, with a topological distance equal to 4  
The last column represents the estimate of the BCF on a logarithmic scale, calculated experimentally, and so on the basis of this, in the penultimate column we find the actual class of the substance.
