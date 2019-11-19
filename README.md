# Uhlig_Toolkit_in_Python

A Simple Toolkit for Computational Analysis: Solving linear approximations of dynamic stochastic general equilibrium (DSGE) models in Python

An abbreviated translation from MATLAB into Python of Harald Uhlig's solution method, as described in "A Tooklit for Analyzing Nonlinear Dynamic Stochastic Models Easily," Discussion Paper 101, Federal Reserve Bank of Minneapolis, June 1995 (1997) and in his MATLAB code (1995 - 2003). 

For more on Uhlig's toolkit see  https://www.wiwi.hu-berlin.de/de/professuren/vwl/wipo/research/MATLAB_Toolkit


CONTENTS OF THIS REPOSITORY:

* 'uhlig_solver_abreviated.ipynb'  Uhlig's solver algorithm using the generalized eigenvalue eigenvector method

* 'uhlig_solver_QZ.ipynb'  Uhlig's solver algorith using a QZ decomposition as discussed by:

  * Chris Sims in "Solving Linear Rational Expectations Models," Computational Economics, October 2002, Vol 20, Issue 1-2, pp 1-20, and in his MATLAB code qzdiv.m and qzswitch.m.  For more of Sim's work: http://www.princeton.edu/~sims/  
  
  * Paul Klein "Using the Generalized Schur Form to Solve a Multivariate Linear Rational Expectations Model,"  Journal of Economic Dynamics and Control, 24 (2000) 405-1423.  For more of Klein's work:  http://paulklein.ca/newsite/codes/codes.php  

* Other programs:  Calc_Moments.ipynb, Detrend_Filters.ipynb, uhlig_impulse_resp_all.ipynb, uhlig_plot_impresp_all.ipynb, uhlig_simul_rand.ipynb, uhlig_plot_simul_all.ipynb

* Unsolved examples:  uhlig_example_xx.ipynb

* Solved examples with impulse responses:  za_impresp_example_xx.ipynb

* Solved examples with simulations, given randomly generated innovations:  zb_simul_example_xx.ipynb

* Solved examples filtered into trend and cyclical components with calculated moments for cyclical components:  zc_detmom_example_xx.ipynb 

* Solved examples using a QZ decomposition:  zd_qzsoln_example_xx.ipynb


NOTES:

Generalized Eigenvalue Eigenvector Method:

* As a check, I ran the examples using both my Python code and Uhlig's MATLAB code. I then compared the output matrices, i.e. PP, QQ, RR, SS, Resp_mat, and verified that these are identical for all models.  
* I also compared intermediate matrices, including Psi_mat, Gamma_mat, Theta_mat, Xi_mat, Delta_mat, Lambda_mat, Omega_mat, which are nearly identical for all models.  
* Exceptions occur in the intermediate matrices eVecs (Xi_eigvec) and eVals (Xi_eigval) because eigenvalues and eigenvectors computed in Python (numpy.linalg.eig() function) do not always coincide with MATLAB (eig() function). However, the results of both Python and MATLAB eigenvalue and eigenvector computations appear to be true and differences are not due to discrepancies in precision. 
* These differences have no impact on the solution output of examples 00, 01, 02, 03, 06 and 07.  Similarly, these do not matter for 'Models 1 and 2' of examples 04 and 05. 
* In contrast, they do result in different intermediate and output matrices for 'Model 3 with Sunspots' of example 05.  For instructional purposes, Uhlig set-up 'Model 3' of example 04 incorrectly and the model hangs when solved. He showed the correction in example 05. 

QZ Decomposition:

*  Using MATLAB,  all examples have identical solution results for the generalized method and the QZ decomposition.
*  For the most part, the QZ decomposition in Python yields similar results to the QZ decomposition in MATLAB.
*  However,  there are small discrepancies in the intermediate matrices for examples 03, 04_01, 05_02 and 07.  But these are small enough so that the final output matrices are the same.
*  For example 05_03, however, both intermediate matrices and final output matrices are noticeably different.

