# DNA-sequencing-using-machine-learning

# Introduction

* DNA is widely considered the blueprint of life. The instructions required for all life forms, to evolve, breed, and thrive are found in DNA. 
* A biological macromolecule is DNA, also known as deoxyribonucleic acid. Life's blueprint is encoded by it. The instructions required for a creature to grow, endure, and reproduce are encoded in its DNA. 
* Sequencing of DNA has exponentially progressed due to the immense increase in the production of data in today’s world. By means of this paper, we present a comparative analysis of past DNA Sequencing techniques to the Modern Day applications that incorporate Machine Learning Models.

# DNA Structure

* The DNA structure can be thought of as a twisted ladder. This structure is described as a double-helix. 
* It is a nucleic acid, and all nucleic acids are made up of nucleotides. The DNA molecule is composed of units called nucleotides, and each nucleotide is composed of three different components such as sugar, phosphate groups and nitrogen bases. 
The sugar and phosphate groups link the nucleotides together to form each strand of DNA. Adenine (A), Thymine (T), Guanine (G)  and Cytosine (C) are four types of nitrogen bases.
* These 4 Nitrogenous bases pair together in the following way: A with T, and C with G. These base pairs are essential for the DNA’s double helix structure, which resembles a twisted ladder.

# Past Techniques 

* Sanger Sequencing: Sanger and Coulson developed a sequencing method known as enzyme DNA sequencing or Sanger sequencing in the ’70s this will be utilizing DNA polymerase which is different from the previous non-enzymatic approach.
* NGS Bioinformatics: When compared to the old techniques the data has increased a lot and it is required to continue to develop informatics algorithms that will be translating the results of the DNA sequencing and the NGS platform will be analyzing and manage the data which is generated using statistical methods and bioinformatics tools.

# Evolution of Techniques 

* Third-Generation Sequencing: The Third Generation Sequencing can sequence single molecules of DNA without the need for clonal amplification prior to sequencing. This will be avoiding the introduction of artifacts from the PCR and this will require less manipulation of the sample.
* Applications of Next-generation sequencing: There are many types of sequencing such as whole genome resequencing, targeted resequencing, gene expression analysis with whole transcriptome analysis, small RNA sequencing, and methylation analysis.

# Modern-Day DNA Sequencing using Machine Learning 

## Flowchart

![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/dd486352-8b60-40a9-aa68-a65e9f44e3e0)

## Dataset Description

* We take an exploratory dataset (Chauhan, DNA sequence dataset 2021) from Kaggle. It consists of 3 organisms - Human, Chimpanzee, and Dog and seven gene families as stated below:

![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/3c5878f1-95d5-4b1c-bc3e-55f5af1cb6da)

## Data Preprocessing

* Standardizing file formats and displaying DNA sequences in classes. For example below we see the class Distribution of Human DNA from our dataset.

![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/0ceef791-835c-4921-a491-b407cb2053b8)

## Data Cleaning

* Small letters should be used for all sequence characters. If DNA contains any characters that are not in (A, C, G, or T), put them in as (z) characters.

![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/8da220f6-f881-4878-9f5e-bd40c1faec4c)

## Feature Engineering

### K-mer counting DNA language

* A metaphorical comparison to the language of life would be DNA and protein sequences. For the molecules that are present in all living things, language also carries instructions for how they should function. With the genome serving as the book, subsequences (genes and gene families) serving as the sentences and chapters, k-mers and peptides (motifs) serving as the words, and nucleotide bases and amino acids serving as the alphabet, the sequence language analogy continues. Given how appropriate the parallel looks, it makes sense that the incredible work done in the field of natural language processing would also apply to the natural language of DNA and protein sequences.

* Here, we employ a straightforward and easy strategy. We first divide the lengthy biological sequence into overlapping k-mer length "words." If we use "words" of length 6 (hexamers), for instance, "ATGCATGTCA" becomes "TGCATG",  ATGCAT," "GCATGC," and "CATGCA." In light of this, our example sequence is divided into 4 hexamer words. These types of modifications are referred to as "k-mer counting" in genomics, which is the process of counting the occurrences of each potential k-mer sequence.

![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/481ab6de-1557-45cb-9396-0d9bce25830e)

* We next use the Scikit-Learn natural language processing tools to perform the k-mer counting; however, in order to apply the count vectorizer, we must first convert the lists of k-mers for each gene into string sentences of words.

* The Bag of Words model is now developed using CountVectorizer. Earlier testing established the n-gram size of 4. 

* We have 4380 genes for humans that have been transformed into 232414 feature vectors of uniform length measuring 4-gram k-mer (length 6) counts. With 1682 and 820 genes respectively, chimpanzees and dogs both share the same number of features.


![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/8da0e75e-b786-4644-af06-6567c70e71ea)


![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/6c5e970d-4009-4237-b9cb-c88b25a30595)

## Splitting the human dataset into the training set and test set

* The final preprocessing step is to separate the data into training and test sets once it has been separated into inputs and labels. The "train test split" method from the "model selection" library of the "Scikit-Learn library" enables us to easily split data into training and test sets with 80% Train dataset & 20% Test dataset.
* Thus we have 3504 sequences in the training data and 876 sequences in the testing data.


![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/0b5ffb44-7045-42a6-8fa0-d225f1870119)

## Model Selection:

Our next step is to build a Multinomial Naive Bayes classifier. The most effective n-gram size and model alpha are 4 and 0.1, according to prior parameter tuning results.



![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/90600a65-b312-4d9f-b3f3-7a59b6676ced)

## Evaluation Metrics


![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/4d8dfc22-c262-4909-a80c-71d62bd5c85a)

## Result Analysis:


![image](https://github.com/Khizar-Baig/DNA-sequencing-using-machine-learning/assets/59732957/34c1b745-532d-4457-b1a2-4232a373ca2f)

# Future Scope

* Technology is increasing and the techniques for DNA sequencing are increasing.
* Epigenomic variation is an extension of genome resequencing applications and this will also be investigated using the next-generation sequencing approaches which will enable the ascertainment of genome-wide patterns of methylation and the organism’s development will be based on the patterns that change through the course.
* If the DNA sequencing is done rapidly then the experiment results will enhance the potential to combine the results of different experiments and this is the most exciting possibility. The secrets of the cell can be unlocked with the power of correlative analysis, correlative analysis of the genome-wide methylation, histone binding patterns, and gene expression for instance owing to the data that is produced similarly.

# Conclusion

* It is evident that the New-Age DNA Sequencing techniques are exponentially more efficient than the past techniques. The 98.4% accuracy of our model is staggering proof of this claim. Hence it can be noted that the field of bioinformatics and genomics has made substantial progress.

* This small step of Machine Learning incorporation into the Sequencing techniques can very well be a giant leap forward in solving major global illnesses. This along with the rapid development of the Genetic Engineering Domain could be the key to discovering a cure for the threats such as Cancer or hereditary disorders.

# References

* Mohamed, O. (2021, April 5). DNA sequencing with Machine Learning. DataValley. Retrieved December 20, 2022, from https://datavalley.technology/dna-sequencing-with-machine-learning/ 
* Chauhan, N. S. (2021, January 15). DNA sequence dataset. Kaggle. Retrieved December 20, 2022, from https://www.kaggle.com/datasets/nageshsingh/dna-sequence-dataset 
Gu, M. (2021, September 6). DNA sequence classification based on Milvus. Milvus. Retrieved December 21, 2022, from https://milvus.io/blog/dna-sequence-classification-based-on-milvus.md 
* Dixit, P., & Prajapati, G. I. (2015). Machine Learning in Bioinformatics: A novel approach for DNA sequencing. 2015 Fifth International Conference on Advanced Computing & Communication Technologies. https://doi.org/10.1109/acct.2015.73
* Sarkar, S., Mridha, K., Ghosh, A., Shaw, R.N. (2022). Machine Learning in Bioinformatics: New Technique for DNA Sequencing Classification. In: Shaw, R.N., Das, S., Piuri, V., Bianchini, M. (eds) Advanced Computing and Intelligent Technologies. Lecture Notes in Electrical Engineering, vol 914. Springer, Singapore. https://doi.org/10.1007/978-981-19-2980-9_27  
* Shendure, J., Balasubramanian, S., Church, G. M., Gilbert, W., Rogers, J., Schloss, J. A., &amp; Waterston, R. H. (2017). DNA sequencing at 40: Past, present and future. Nature, 550(7676), 345–353. https://doi.org/10.1038/nature24286 
* Mardis, E. R. (2008). Next-generation DNA sequencing methods. Annual Review of Genomics and Human Genetics, 9(1), 387–402. https://doi.org/10.1146/annurev.genom.9.081307.164359 
* Morey, M., Fernández-Marmiesse, A., Castiñeiras, D., Fraga, J. M., Couce, M. L., & Cocho, J. A. (2013). A glimpse into past, present, and future DNA sequencing. Molecular Genetics and Metabolism, 110(1-2), 3–24. https://doi.org/10.1016/j.ymgme.2013.04.024 























