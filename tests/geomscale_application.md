### first thoughts and tentative task list for Spectrahedra R Interface project

- aim is to update Rvolesti sample_points and volume functions to support spectrahedra
- how are spectrahedra mathematically different from other polytopes supported by these two functions 
- how is spectrahedra class different from classes representing other types of polytopes
- choosing appropriate sampling distributions - uniform, gaussian, log-concave
- choosing appropriate random walks from the various options volesti offers

#### milestones or tasks

- generate cran package of rvolesti, compile and run the package (easy test)
- read this paper - Sampling the feasible sets of SDPs and volume approximation - Chalkis, Fisikopoulos, Repouskos, Tsigaridas, 2020 pdf
- modifying an existing Rcpp function in Rvolesti to provide a new option to the user, like printing additional information or intermediate outputs or changing the format of the outputs. (hard test)
- going through different functions of volume computation and random walk for different polytopes
- using these examples as templates for pseudo code
- converting pseudo-code into sub-function that is called within sample_points and volume
- what are the current methods for doing this for spectrahedra, what are the standards for accuracy and efficiency; from other libraries or research papers


### first thoughts and tentative task list for AutoDiff R Interface project
- volesti automatically constructs the procedure of computing derivatives of a function using the autodiff library
- the aim of the project is to provide R interface for volesti C++ routines doing automatic differentiation, through Rvolesti function sample_points, so that only distribution function needs to be provided, and not its derivative

#### milestones or tasks
- generate cran package of rvolesti, compile and run the package (easy test)
- read up on automatic differentiation https://en.wikipedia.org/wiki/Automatic_differentiation
- read up on autodiff library
- identify which sections of volesti codebase are related to automatic differentiation, and which functions and objects from autodiff library are called for
- identify which parts of the Rvolesti function sample_points relies on the derivative of the distribution
- writing pseudo-code which relies on volesti C++ routines to provide that derivative,
- converting pseudo code to R/RCpp functions
- write tests to compare user-provided derivatives to derivatives generated from volesti
- tests for different distribution functions and different random walks

### tests done - 
1. compiled C++ version of volesti, and run tests. output [here](tests/new_volume_example_output.txt)
2. built and run R interface of volesti

#### currently stuck on - 
this compilation was done on Debian (using WSL2 on Windows 10). however i have not been able to replicate these since, most likely due to memory issues.

#### possible solution - 
- i am currently trying to recreate the set up on Windows 10 
- it might be useful to break up the tests for volesti in two or three batches as execution always gets stuck on the 63rd test
- google colab (and other cloud platforms) supports R. however it is not possible to read external folders directly, only individual files using googledrive package from posit. would install_github from devtools be helpful in this situation?
- maybe there is a way to reduce memory usage during build, that i am not aware of? 

### next steps for me
- finish compilation using one of the above methods
- modify an existing Rcpp function
- finalise a project and submit proposal for feedback

### about me:
- email: shumaari2022@gmail.com, (also available on mobile, slack, discord, skype, zoom for messaging or calls)
- location: Bangalore India, timezone: UTC +0530

&nbsp;  

- i have spent the past year studying, (and being Community Teaching Assistant for), fundamentals of Statistics, Probability, Data Analysis for Social Scientists courses as a part of my MITx Micromasters through edX. 
- i am interested in working on projects that are at the intersection of mathematics and coding, which is why geomscale is a perfect fit for me.
- i know i might not be as proficient in maths or computer science as current fulltime students, however i would still like to make my best attempt!

### two questions for you - 
1. choosing a project - which project (spectrahedra vs autodiff) is more important to geomscale in terms of impact? would you prefer me to work on my chosen project (autodiff R interface) or a different project from ideas list so as to not duplicate efforts from other contributors?
2. would you please share some reading material and some sections of the codebase which might be indirectly related and useful for the project?

i look forward to hearing from you guys, in comments below, on email, or gitter :)

