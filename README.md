# ETM-R: R Package for the Embedded Topic Model

(This R package is still under development)

This is an R package to run ETM, a Python-based package that accompanies the paper titled "Topic Modeling in Embedding Spaces" by Adji B. Dieng, Francisco J. R. Ruiz, and David M. Blei (link: https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00325/96463/Topic-Modeling-in-Embedding-Spaces). 

ETM (embedded topic model) defines words and topics in the same embedding space. The likelihood of a word under ETM is a Categorical whose natural parameter is given by the dot product between the word embedding and its assigned topic's embedding. ETM is a document model that learns interpretable topics and word embeddings and is robust to large vocabularies that include rare words and stop words.

For the original Python package, please refer to: https://github.com/adjidieng/ETM.


# How ETM-R Works:

ETM-R provides R users the ability to use ETM without needing to know the Python programming language.  ETM-R provides customized functions in R that are directly translated into Python code to run the ETM. 

ETM-R provides four steps to evaluate words and topics in a corpus.  
1) Preprocessing: converting a raw text file or corpus into a bag-of-words representation (e.g. tokens and counts).  
2) Embeddings: fitting word embeddings (numerical representations of text) onto the text.
3) Modeling: applying the embedded topic model onto the preprocessed corpus and the fitted word embeddings to produce interpretable topics.  
4) Evaluation: evaluating the topic diversity and coherence of the corpus, and visualizing the top results of the topics.

# Benefits of ETM-R
1) No prior knowledge of Python.  All of the necessary installations (even installing Python!) and Python scripts are executed in an R console using R functions.
2) Speed and efficiency.  The original ETM Python code is optimized for speed and efficiency.  As ETM-R is executing the same underlying Python code, users of ETMr will expect the same level of speed and efficiency.
3) Customizable applications.  ETMr can be applied on any corpus using the convenient R functions provided in this package.

# How to use ETM-R
1) To start, run the function `start_etm()`, which launches a Python environment that is usable in the R console.
2) For the preprocessing step, use: `etm_preprocess()`, which converts the 
3) For the embeddings step, use: `etm_embed()`, which uses Word2Vec to fit embeddings to the corpus.  Current embedding methods are skipgrams and continuous bag-of-words (CBOW).  If you are using a corpus with pre-fitted embeddings, ignore this step.
4) For the modeling step, use: `etm_prefit()`, which runs the ETM algorithm on text with the pre-fitted word embeddings from the previous step.
5) For the evaluation step, use: `etm_evaluate()`, which evaluates perplexity on document completion, topic coherence and topic diversity.  This step also allow visualizations of the embeddings and the topics on a 2-dimensional embeddings space, which would show the distance between the topic of choice and a collection of key words.

An alternative method is to use `etm_model()`, which combines the embeddings and modellings steps into a single step.


# How to install in R 
Install the R package using `devtools::install_github`:

```
   install.packages("devtools")
   install_github("p-lin/ETM-R")
```
Upon installation, ETM-R will detect to see if there is a version of Python available on the local machine.  If not, ETM-R will ask to install Miniconda, a minimal distribution that installs Python.  ETM-R will then install all of the necessary Python packages for the Python-based ETM package.



## Citation

```
@article{10.1162/tacl_a_00325,
    author = {Dieng, Adji B. and Ruiz, Francisco J. R. and Blei, David M.},
    title = "{Topic Modeling in Embedding Spaces}",
    journal = {Transactions of the Association for Computational Linguistics},
    volume = {8},
    pages = {439-453},
    year = {2020},
    month = {07},
    abstract = "{Topic modeling analyzes documents to learn meaningful patterns of words. However, existing topic models fail to learn interpretable topics when working with large and heavy-tailed vocabularies. To this end, we develop the embedded topic model (etm), a generative model of documents that marries traditional topic models with word embeddings. More specifically, the etm models each word with a categorical distribution whose natural parameter is the inner product between the word’s embedding and an embedding of its assigned topic. To fit the etm, we develop an efficient amortized variational inference algorithm. The etm discovers interpretable topics even with large vocabularies that include rare words and stop words. It outperforms existing document models, such as latent Dirichlet allocation, in terms of both topic quality and predictive performance.}",
    issn = {2307-387X},
    doi = {10.1162/tacl_a_00325},
    url = {https://doi.org/10.1162/tacl\_a\_00325},
    eprint = {https://direct.mit.edu/tacl/article-pdf/doi/10.1162/tacl\_a\_00325/1923074/tacl\_a\_00325.pdf},
}
```
