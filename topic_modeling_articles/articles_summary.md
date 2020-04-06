# Topic Modeling articles
> This file contains summaries of topic modeling articles

## Table of contents
1. [Vorontsov topic modeling survey](#vorontsov-survey)
2. [Interpretable probabilistic embeddings](#interpretable-probabilistic-embeddings)


## Vorontsov survey
> [Link to article](http://www.machinelearning.ru/wiki/images/d/d5/Voron17survey-artm.pdf)
* pLSA (Probabilistic Latent Semantic Analysis) 
    *  Topic model is learned by log-likelihood maximization
        * <img src="https://render.githubusercontent.com/render/math?math=$\sum_{d \in D} \sum_{w \in d} n_{d w} \ln \sum_{t \in T} \phi_{w t} \theta_{t d} \rightarrow \max _{\Phi, \Theta},  where \enspace \phi_{w t}=p(w | t) \enspace \theta_{t d}=p(t | d) \enspace \Phi=\left(\phi_{w t}\right)_{W \times T} \enspace \Theta=\left(\theta_{t d}\right)_{T \times D}$">
    * The parameters can be trained with EM algorithm
    * The model is prone to overfitting 
      
* LDA (Latent Dirichlet Allocation)
    * In comparison with pLSA initialize vectors in EM algorithm (which generate randomly) <img src="https://render.githubusercontent.com/render/math?math=$\phi_{t} \enspace and \enspace \theta_{d}$"> are drawn from Dirichlet distributions with hyperparameters <img src="https://render.githubusercontent.com/render/math?math=$\beta=\left(\beta_{w}\right)_{w \in W} \enspace and \enspace \alpha=\left(\alpha_{t}\right)_{t \in T} $"> respectively
    * LDA spans a hyperspace and is therefore generalizable to unseen documents
    * Uses a variational Bayes approximation of the posterior distribution
    * The problem is that the thematic modeling problem has a lot solutions, and the LDA chooses one of them, without providing any means to choose the best solution for a specific task
* ARTM (Additive Regularization of Topic Models)
    * Solves the problem described above due to regularizations
    * <img src="https://render.githubusercontent.com/render/math?math=$L(\Phi, \Theta)+R(\Phi, \Theta) \rightarrow \max _{\Phi, \Theta}$">
    * <img src="https://render.githubusercontent.com/render/math?math=$R(\Phi, \Theta)=\sum_{i=1}^{n} \tau_{i} R_{i}(\Phi, \Theta), \enspace where \enspace \tau_{i} - non-negative \enspace regularization  \enspace coefficient \enspace and \enspace R_{i}(\Phi, \Theta) - one \enspace of \enspace the \enspace regularizers$">
    * Regularizers:
        * Smooth term distributions in topics
        * Smooth distribution of topics in documents
        * Sparse term distributions in topics
        * Sparse distribution of topics in documents
        * Decorrelating term distributions in topics
        * Selection by zeroing the probability of the topic in all documents

    


## Interpretable probabilistic embeddings
> [Link to article](https://arxiv.org/pdf/1711.04154.pdf)

TBD