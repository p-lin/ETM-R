# ETM-R
R Package for ETM

(This R package is still under development.  The package may or may not be usable in its current state).

This is an R package to run ETM, a Python-based package that accompanies the paper titled "Topic Modeling in Embedding Spaces" by Adji B. Dieng, Francisco J. R. Ruiz, and David M. Blei (link: https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00325/96463/Topic-Modeling-in-Embedding-Spaces). 

ETM (embedded topic model) defines words and topics in the same embedding space. The likelihood of a word under ETM is a Categorical whose natural parameter is given by the dot product between the word embedding and its assigned topic's embedding. ETM is a document model that learns interpretable topics and word embeddings and is robust to large vocabularies that include rare words and stop words.

ETM-R provides R users the ability to use ETM without needing to know the Python programming language.  ETM-R provides customized functions in R that are directly translated into Python code to run the ETM.  Installation of ETM-R will also provide a chance to install a version of Python (Miniconda), if a version of Python is not automatically detected on the local machine.




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
