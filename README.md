# MVI - Project

**Topic**: Binary classification of normal and cancer-associated fibroblasts from scRNA-Seq

**Author**: Vojtech Melichar, UCT Prague & CTU in Prague, Czech Republic, 2023

## Project description

Single-cell RNA-Seq is a state-of-the-art technique for measuring the transcriptional profile of each individual cell in the tissue sample. Simply put, the transcriptional profile can be seen as a capture of the current state of the cell; it tells us which genes are active and which are turned off. In turn, a particular gene or set of genes can be associated with a disease. However, these *in sillico* results must be validated by further *in vitro* or *in vivo* experiments.

## Data

In this particular experiment, researchers took samples from normal and cancerous tissue. These two classes are the target variable. The intensity of each gene is measured in each cell. This makes up a count matrix, which is used for training and testing of the model. The features correspond to individual genes, and each row is an individual cell. Due to the nature of the experiment, the count matrix has a high level of sparsity. The dataset contains approximately 25k genes and 29k cells and is publicly available.

## Methods

The dataset was split into training, validation and testing datasets, with ration of 50/20/30. The NN was designed in `pytorch`.

There are two main goals in this project. Firstly, create a neural network for binary classification of cells. The size of the input layer is equal to the number of genes in the dataset.

Secondly, rank genes according to importance by recursive feature elimination (RFE). This can return a set of genes with only a few genes that are the best predictors of this type of cancer. 
