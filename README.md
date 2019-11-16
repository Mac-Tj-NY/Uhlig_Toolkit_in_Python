# Uhlig_Toolkit_in_Python

A Simple Toolkit for Computational Analysis: Solving linear approximations of dynamic stochastic general equilibrium (DSGE) models in Python

An abbreviated translation from MATLAB into Python of Harald Uhlig's solution method, as described in "A Tooklit for Analyzing Nonlinear Dynamic Stochastic Models Easily," Discussion Paper 101, Federal Reserve Bank of Minneapolis, June 1995 (updated 1997) and in his MATLAB code (1995 - 2003). 

For more on Uhlig's toolkit see  https://www.wiwi.hu-berlin.de/de/professuren/vwl/wipo/research/MATLAB_Toolkit


CONTENTS OF THIS REPOSITORY:

* 'uhlig_solver_abreviated.ipynb'  Uhlig's solver algorithm using the generalized eigenvalue/eigenvector method

* Other programs:  Calc_Moments.ipynb, Detrend_Filters.ipynb, uhlig_impulse_resp_all.ipynb, uhlig_plot_impresp_all.ipynb, uhlig_simul_rand.ipynb, uhlig_plot_simul_all.ipynb

* Unsolved examples:  uhlig_example_xx.ipynb

* Solved examples with impulse responses:  za_impresp_example_xx.ipynb

* Solved examples with simulations, given randomly generated innovations:  zb_simul_example_xx.ipynb

* Solved examples filtered into trend and cyclical components with calculated moments ofr cyclical components:  zc_detmom_example_xx.ipynb 


NOTE:

* As a check, I ran the examples using both my Python code and Uhlig's MATLAB code. I then compared the output matrices, i.e. PP, QQ, RR, SS, Resp_mat, and verified that these are identical for all models.  
* I also compare  intermediate matrices, including Psi_mat, Gamma_mat, Theta_mat, Xi_mat, Delta_mat, Lambda_mat, Omega_mat, which are nearly identical for all models.  
* The exceptions occur in eVecs (i.e. Xi_eigvec) and eVals (i.e. Xi_eigval), because eigenvalues and eigenvectors computed in Python do not always coincide with MATLAB. However, the results of both eigenvalue and eigenvector computations appear to be true and differences in results are not due to differences in precision. These differences have no impact on the solution output of examples 00, 01, 02, 03, 06 and 07.  Similarly, these do not appear to matter for 'Model 1' of example 05. In contrast, they do result in different intermediate and output matrices for 'Model 3 with Sunspots' of example 05.


