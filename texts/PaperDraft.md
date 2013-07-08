Learning Polynomial Regression with Genetic Algorithms
======================================================

Francisco Coelho |  | João Neto
:---------------:|-----|:---------:
[`fc@di.uevora.pt`](mailto://fc@di.uevora.pt)| |[`jpn@di.fc.ul.pt`](mailto://jpn@di.fc.ul.pt)


**Abstract**  

Many applications require models that have no acceptable linear approximation and many nonlinear models are defined by polynomials. The use of genetic algorithms to find the parameters of a polynomial model is decades old but still poses challenges due to the complexity of the search and different definitions of "optimal" solution.

GIVE A SUMMARY DESCRIPTION AND RESULTS OF "OUR" APPROACH.

Introduction
------------

With notable exceptions, most machine learning techniques are based on linear models. This assumption has many advantages including, for example, reduced computational complexity and strong theoretical framework. However many application scenarios pose nonlinear problems that have no acceptable linear approximations.  
GIVE EXAMPLES AND EXPLAIN WHY LINEAR MODELS FAIL IN THOSE EXAMPLES.

Polynomials, one of the most studied subjects in mathematics, generalize linear models and are, perhaps, one of the simplest and most used nonlinear models. Applications of (nonlinear) polynomial models include colorimetric calibration [APPL1-2005], finding explicit formulae for turbulent pipe flows [APPL2-1999], computational linguistics [APPL8-2009] and more recently, analytical techniques for cultural heritage materials [APPL3-2010], liquid epoxy molding process [APPL4-2011], B-spline surface reconstruction [APPL5-2012], product design [APPL6-2012] or forecasting cyanotoxins presence in water reservoirs [APPL7-2013]. Besides the huge range of quite different areas, the work for each one of these polynomial models used, somewhere, a genetic algorithm.

Genetic algorithms (GA), are perhaps one of the most popular "buzzwords" of recent decades but with good reason since they outline an optimization scheme easy to conceptualize and with very broad application. If a nonlinear model requires parameterization, GAs provide a simple and often effective approach to search for localy optimal parameters. Research related to genetic algorithms abound and spans from the 1950's seminal work of Nils Aall Barricelli in the Institute for Advanced Study of Princeton to today's principal area of study of thousands of researchers, covered in hundreds of conferences, workshops and other meetings. Perhaps the key impulse to GAs come from John Holland and his book [BOOK-JOHNHOLLAND]. One interesting "flavour" of genetic algorithms, termed "genetic programming" by John Koza, proposed the use of GAs to search the syntatic stucture of complex functions. This syntatic structure search is keen to the central ideas of deep learning, the subarea of machine learning actually producing the most advanced results.  
INSERT MORE REFERENCES OF RECENT GA RESEARCH AND DEEPLEARNING RESULTS

**END** STATE-OF-THE-ART

SUMMARIZE OUR PROBLEM STATEMENT, EXPLAIN WHY IT IS IMPORTANT, OUR RESOLUTION, EVALUATION STRATEGY AND RESULTS.

Polynomial Regression with Genetic Algorithms
---------------------------------------------

HOW DO WE DO THE
* polynomial encoding
* cost function
* genetic operators
* selection of other search parameters (_eg_ population size, maxiter, _etc_)


### Polinomial Encoding

_Describe our method to encode polynomial instances_

### Cost Function

_Define the cost function_

Given a dataset $D=\left\lbrace x_1^{(i)}, \ldots, x_m^{(i)}, y^{(i)} \in \mathbb{R}^{m+1} : i = 1,\ldots, n \right\rbrace$ with $n$ observations of $m+1$ variables $X_1, \ldots, X_m, Y$. We want to find a polynomial that fits $y = h\left( x_1, \ldots, x_m\right)$ and for that purpose we apply the usual _root-mean-square error_ as a cost function of a candidate fitting polynomial $h_{\Theta}$ defined by parameters $\Theta$:
$$
J_{fit}\left( \Theta; D \right) = \frac{1}{n} \sum_{i=1}^n \left( y^{(i)} - h_{\Theta}\left(x_1^{(i)}, \ldots, x_m^{(i)}\right) \right)^2
$$

### Genetic Operators

_Define the genetic operators_

### Other Search Parameters

_Explain the remaining search parameters_

Results
-------

* Measured quantities
  - error
  - number of iterations to convergence
  - memory usage
  - F1, ROC, ?  
* Selection of datasets and regression algorithms
* Summary Figures and Numeric results

Conclusion
----------


References
----------

1. Ghai, Dhruva, Saraju P. Mohanty, and Garima Thakral. "Fast Analog Design Optimization using Regression based Modeling and Genetic Algorithm: A Nano-CMOS VCO Case Study." Proceedings of the 14th IEEE International Symposium on Quality Electronic Design (ISQED). 2013.

1. Rezania, Mohammad, Akbar A. Javadi, and Orazio Giustolisi. "Evaluation of liquefaction potential based on CPT results using evolutionary polynomial regression." Computers and Geotechnics 37.1 (2010): 82-92.

1. Zain, Azlan Mohd, Habibollah Haron, and Safian Sharif. "Genetic algorithm and simulated annealing to estimate optimal process parameters of the abrasive waterjet machining." Engineering with computers 27.3 (2011): 251-259.

1. Garg, A., and K. Tai. "Comparison of regression analysis, artificial neural network and genetic programming in handling the multicollinearity problem." Modelling, Identification & Control (ICMIC), 2012 Proceedings of International Conference on. IEEE, 2012.


[GAPOLY1-2011] http://dx.doi.org/10.4203/ccp.97.39 "Optimal Polynomial Regression Models by using a Genetic Algorithm"

[GAPOLY2-2008] http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.152.7415 "Optimal Sampling of Genetic Algorithms on Polynomial Regression"

[GAPOLY3-2011] http://www.eejournal.ktu.lt/index.php/elt/article/view/460 "Polynomial Curve Fitting with Varying Real Powers"

[GAPOLY4-2009] http://dx.doi.org/10.1016/j.eswa.2008.06.046 "A Novel hybrid genetic algorithm for kernel function and parameter optimization in support vector regression"

[GAPOLY5-2006] http://dx.doi.org/10.1007/s00500-005-0008-8 "Genetic polynomial regression as input selection algorithm for non-linear identification"

[APPL1-2005]: http://dx.doi.org/10.1109/WISP.2005.1531626 "Adaptive polynomial regression for colorimetric scanner calibration using genetic algorithms"

[APPL2-1999]: http://www.environmental-expert.com/Files/5302/articles/5912/art-4.pdf "Method for the identification of explicit polynomial formulae for the friction in turbulent pipe flow"

[APPL3-2010]: http://discovery.ucl.ac.uk/459862/1/459862_Csefalvayova_2010_Talanta_EPS.pdf "Use of genetic algorithms with multivariate regression for determination of gelatine in historic papers based on FT-IR and NIR spectral data"

[APPL4-2011]: http://dx.doi.org/10.1109/TII.2010.2100130 "Modeling of a liquid epoxy molding process using a particle swarm optimization-based fuzzy regression approach"

[APPL5-2012]: http://dx.doi.org/10.1016/j.ins.2010.09.031 "Iterative two-step genetic-algorithm-based method for efficient polynomial B-spline surface reconstruction"

[APPL6-2012]: http://dx.doi.org/10.1007/978-3-642-27476-3_6 "Development of Product Design Models Using Fuzzy Regression Based Genetic Programming"

[APPL7-2013]: http://dx.doi.org/10.1016/j.envres.2013.01.001 "Hybrid modelling based on support vector regression with genetic algorithms in forecasting the cyanotoxins presence in the Trasona reservoir (Northern Spain)"

[APPL8-2009]: http://dx.doi.org/10.1007/s00500-008-0362-4 "Obtaining linguistic fuzzy rule-based regression models from imprecise data with multiobjective genetic algorithms"

[BOOK-JOHNHOLLAND]: http://mitpress.mit.edu/books/adaptation-natural-and-artificial-systems "Adaptation in Natural and Artificial Systems"