# Exploring Polynomial Structure of Data with Genetic Algorithms

(alternative title: Selection of Polynomial Features by Genetic Algorithms)

Francisco Coelho |  | João Neto
:---------------:|-----|:---------:
[`fc@di.uevora.pt`](mailto://fc@di.uevora.pt)| |[`jpn@di.fc.ul.pt`](mailto://jpn@di.fc.ul.pt)


>Antes de submeter, temos de considerar [Polynomial regression na wikipedia](http://en.wikipedia.org/wiki/Polynomial_regression) e a [regressão não-linear em geral](https://www.google.pt/search?q=nonlinear+regression).  
>
>Como este trabalho anda no meio de áreas muito trabalhadas, temos de ter muito cuidado com a questão da **investigação original**.
> 
> Sanity check  before merging...

**Abstract**  

Many applications require models that have no acceptable linear approximation and many nonlinear models are defined by polynomials. The use of genetic algorithms to find polynomial models is decades old but still poses challenges due to the complexity of the search and different definitions of "optimal" solution.
This work describes a general method based in genetic algorithms to find "empirical" polynomial regressions.

GIVE A SUMMARY DESCRIPTION AND RESULTS OF "OUR" APPROACH.

## Introduction

With notable exceptions (_e.g._ neural networks), most machine learning regression techniques are based on linear models. This assumption has many advantages including, for example, reduced computational complexity and strong theoretical framework. However nonlinearity in unavoidable in many application scenarions _e.g._ phase transitions or systems with feedback loops so common in ecology, cybernetics, robotics and other areas. Nevertheless the variety and number of phenomena that can be adapted into a linear model is amazing.

Polynomials, one of the most studied subjects in mathematics, generalize linear functions and define, perhaps, the simplest and most used nonlinear models. Applications of polynomial include colorimetric calibration ([APPL1-2005]), explicit formulae for turbulent pipe flows ([APPL2-1999]), computational linguistics ([APPL8-2009]) and more recently, analytical techniques for cultural heritage materials ([APPL3-2010]), liquid epoxy molding process ([APPL4-2011]), B-spline surface reconstruction ([APPL5-2012]), product design ([APPL6-2012]) or forecasting cyanotoxins presence in water reservoirs ([APPL7-2013]). Besides the huge range of quite different areas, the work for each one of these polynomial models used, somewhere, a genetic algorithm.

Genetic algorithms (GA) where, arguably, one the most popular "hot" topics of research in the recent decades but with good reason since they outline an optimization scheme easy to conceptualize and with very broad application. If a nonlinear (or otherwise) model requires parameterization GAs provide a simple and often effective approach to search for localy optimal parameters. Research related to genetic algorithms abound and spans from the 1950's seminal work of Nils Aall Barricelli ([BARRICELLI-1962]) in the Institute for Advanced Study of Princeton to today's principal area of study of thousands of researchers, covered in hundreds of conferences, workshops and other meetings. Perhaps the key impulse to GAs come from John Holland's work and his book ([BOOK-JOHNHOLLAND]).  

One interesting "flavour" of genetic algorithms, named _genetic programming_ by John Koza ([KOZA1-1992]), proposed the use of GAs to search the syntatic stucture of complex functions. This syntatic structure search is keen to the central ideas of deep learning ([DEEPLEARNING1-2012] and [DEEPLEARNING2-2009]), the subarea of machine learning actually producing the most promising results (e.g. [DLAPPL1-2013]). It is also related to the work presented in this paper in the sense that, unlike linear models that have a simple structure ($y=\sum_i \beta_i x_i$) nonlinear (in particular polynomial) models pose an aditional "structure" search problem.

The idea of using GAs to find a polynomial regression is not new ([GAPOLY5-2006], [GAPOLY2-2008] and [GAPOLY4-2009]) but still generates original research ([GAPOLY1-2011] and [GAPOLY3-2011]). In line with that research this work describes a general method to find a polynomial regression of a given dataset. The optimal regression minimizes a cost function that accounts for both the _mean square error_ and a _regularization_ factor to avoid overfitting by penalizing polynomials that are "too complex". 

A method that produces adequate models "directly" from observed complex data has many uses. For example by a scientist to better understand the source of the data or by an autonomous agents adapting to the environment.  
MORE REASONS?  

RESULTS OUTLINE  

The remainder of this paper is organized as usual: the next section describes the details of our method and is followed by a presentation of some performance results. The last section draws some conclusions and points future research tasks.

## Polynomial Regression with Genetic Algorithms

The canonical representation of a polynomial is a sum
$$
p\left( x_1, \ldots, x_k\right) = \sum_i \beta_i m_i.
$$

In this sum each $m_i$ is a monomial, $m_i = \prod_{j\in A_i} x_j^{\alpha_{ij}}$, the exponents are non-negative integers, $\alpha_{ij}\in\mathbb{N}_0$, and the coeficients are real valued, $\beta_i \in \mathbb{R}$. For example $p\left( x_1, x_2, x_3 \right) = 2 x_1 + x_2 x_3 + \frac{1}{2} x_1^2 x_3$ has monomials $m_1 = x_1, m_2 = x_2 x_3$ and $m_3 = x_1^2 x_3$ coefficients $\beta_1 = 2, \beta_2 = 1$ and $\beta_3 = 1/2$ and exponents $\alpha_{1,1} = 1, \alpha_{2,2}=1, \alpha_{2,3} = 1, \alpha_{3,1} = 2, \alpha_{3,3} = 1$ and all other $\alpha_{ij} = 0$.



> **NOTA** Este parágrafo deu-me uma ideia: os $\alpha$ definem uma matriz $A$ em que as linhas são monómios e as colunas variáveis; "Multiplicando" esta matriz por um vector, obtemos o polinómio: $P=CA$. Além disso, podemos continuar a definir a condição de regularização como antes, mas também podemos considerar condições *na* matriz (por exemplo, o número de entradas não nulas ser esparso ou a sua soma ser dominada por $\log nm$)... 


This makes the problem of structure search very clear: except for the trivial cases, the number of possible monomials given $n$ variables and a maximum joint degree $d$ grows exponentialy with either $n$ or $d$. But more importantly, the polynomial regression problem can be split into two subproblems:

1. for a given set of monomials $q_1, \ldots, q_r$, find regression coefficients $\theta_1,\ldots,\theta_r$ that minimize an adequate cost function;
2. find the fittest set of monomials;

Our line of work is to solve the first problem with linear regression and the second with GAs.

[EVALUATION STRATEGY]  

[RESULTS]


HOW DO WE DO THE

* polynomial encoding
* cost function
* genetic operators
* selection of other search parameters (_eg_ population size, maxiter, _etc_)


### Polinomial Encoding

_Describe our method to encode polynomial instances_

### Cost Function

_Define the cost function_

Given a dataset $D=\left\lbrace x_1^{(i)}, \ldots, x_k^{(i)}, y^{(i)} \in \mathbb{R}^{k+1} : i = 1,\ldots, n \right\rbrace$ with $n$ observations of $k+1$ variables $X_1, \ldots, X_k, Y$. To find a polynomial that fits the observations of the dependent variable $Y$ the usual procedure is to explore parameters $\Theta$ of a polynomial hypothesis $h_{\Theta}$ and select a combination that minimizes the _root-mean-square error_ in the dataset $D$:
$$
J_{fit}\left( \Theta; D \right) = \frac{1}{n} \sum_{i=1}^n \left( y^{(i)} - h_{\Theta}\left(x_1^{(i)}, \ldots, x_m^{(i)}\right) \right)^2
$$

Since it is always possible to fit exactly a polynomial to any given dataset, _overfitting_ the available data, a _regularization_ factor is needed to penalyze hypothesis too biased by the training data:

$$
J_{reg} = ?
$$

### Genetic Operators

_Define the genetic operators_

### Other Search Parameters

_Explain the remaining search parameters_

## Results

* Measured quantities
  - error
  - number of iterations to convergence
  - memory usage
  - F1, ROC, ?  
* Selection of datasets and regression algorithms
* Summary Figures and Numeric results

## Conclusion


## References

**the references are defined "here" in the source but hidden in the resulting documents**

1. Ghai, Dhruva, Saraju P. Mohanty, and Garima Thakral. "Fast Analog Design Optimization using Regression based Modeling and Genetic Algorithm: A Nano-CMOS VCO Case Study." Proceedings of the 14th IEEE International Symposium on Quality Electronic Design (ISQED). 2013.

1. Rezania, Mohammad, Akbar A. Javadi, and Orazio Giustolisi. "Evaluation of liquefaction potential based on CPT results using evolutionary polynomial regression." Computers and Geotechnics 37.1 (2010): 82-92.

1. Zain, Azlan Mohd, Habibollah Haron, and Safian Sharif. "Genetic algorithm and simulated annealing to estimate optimal process parameters of the abrasive waterjet machining." Engineering with computers 27.3 (2011): 251-259.

1. Garg, A., and K. Tai. "Comparison of regression analysis, artificial neural network and genetic programming in handling the multicollinearity problem." Modelling, Identification & Control (ICMIC), 2012 Proceedings of International Conference on. IEEE, 2012.

[GAPOLY1-2011]: http://dx.doi.org/10.4203/ccp.97.39 "Optimal Polynomial Regression Models by using a Genetic Algorithm"

[GAPOLY2-2008]: http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.152.7415 "Optimal Sampling of Genetic Algorithms on Polynomial Regression"

[GAPOLY3-2011]: http://www.eejournal.ktu.lt/index.php/elt/article/view/460 "Polynomial Curve Fitting with Varying Real Powers"

[GAPOLY4-2009]: http://dx.doi.org/10.1016/j.eswa.2008.06.046 "A Novel hybrid genetic algorithm for kernel function and parameter optimization in support vector regression"

[GAPOLY5-2006]: http://dx.doi.org/10.1007/s00500-005-0008-8 "Genetic polynomial regression as input selection algorithm for non-linear identification"

[APPL1-2005]: http://dx.doi.org/10.1109/WISP.2005.1531626 "Adaptive polynomial regression for colorimetric scanner calibration using genetic algorithms"

[APPL2-1999]: http://www.environmental-expert.com/Files/5302/articles/5912/art-4.pdf "Method for the identification of explicit polynomial formulae for the friction in turbulent pipe flow"

[APPL3-2010]: http://discovery.ucl.ac.uk/459862/1/459862_Csefalvayova_2010_Talanta_EPS.pdf "Use of genetic algorithms with multivariate regression for determination of gelatine in historic papers based on FT-IR and NIR spectral data"

[APPL4-2011]: http://dx.doi.org/10.1109/TII.2010.2100130 "Modeling of a liquid epoxy molding process using a particle swarm optimization-based fuzzy regression approach"

[APPL5-2012]: http://dx.doi.org/10.1016/j.ins.2010.09.031 "Iterative two-step genetic-algorithm-based method for efficient polynomial B-spline surface reconstruction"

[APPL6-2012]: http://dx.doi.org/10.1007/978-3-642-27476-3_6 "Development of Product Design Models Using Fuzzy Regression Based Genetic Programming"

[APPL7-2013]: http://dx.doi.org/10.1016/j.envres.2013.01.001 "Hybrid modelling based on support vector regression with genetic algorithms in forecasting the cyanotoxins presence in the Trasona reservoir (Northern Spain)"

[APPL8-2009]: http://dx.doi.org/10.1007/s00500-008-0362-4 "Obtaining linguistic fuzzy rule-based regression models from imprecise data with multiobjective genetic algorithms"

[BOOK-JOHNHOLLAND]: http://mitpress.mit.edu/books/adaptation-natural-and-artificial-systems "Adaptation in Natural and Artificial Systems"

[DEEPLEARNING1-2012]: http://arxiv.org/abs/1206.5538 "Representation Learning: A Review and New Perspectives"

[DEEPLEARNING2-2009]: http://www.iro.umontreal.ca/~lisa/publications2/index.php/publications/show/239 "Learning Deep Architectures for AI"

[KOZA1-1992]: http://mitpress.mit.edu/books/genetic-programming "Genetic Programming: On the Programming of Computers by Means of Natural Selection, by John R. Koza, (1992)"

[BARRICELLI-1962]: http://dx.doi.org/10.1007%2FBF01556771 "Numerical testing of evolution theories : Part I Theoretical introduction and basic tests"

[DLAPPL1-2013]: http://www.cs.toronto.edu/~dtarlow/TarSwerCharSutZem_ICML2013.pdf "Tarlow, Daniel and Sutskever, Ilya and Zemel, Richard S. Stochastic k-Neighborhood Selection for Supervised and Unsupervised Learning. 2013. in Proceedings of the 30th International Conference on Machine Learning (ICML)."