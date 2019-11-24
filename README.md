# Uhlig_Toolkit_in_Python

A Simple Toolkit for Computational Analysis: Solving linear approximations of dynamic stochastic general equilibrium (DSGE) models in Python

An abbreviated translation from MATLAB into Python of Harald Uhlig's solution method, as described in:

 *  "A Tooklit for Analyzing Nonlinear Dynamic Stochastic Models Easily," Discussion Paper 101, Federal Reserve Bank of Minneapolis, June 1995 (1997) and  
 *  in his MATLAB code (1995 - 2003) especially solve.m and solve_qz.m.  For more on Uhlig's toolkit see  https://www.wiwi.hu-berlin.de/de/professuren/vwl/wipo/research/MATLAB_Toolkit

Uhlig made extensive use of the neoclassical growth model extensively as an example.  Before him, Robert King, Charles Plosser and Sergio Rebelo used the neoclassical growth model to develop methods for the  analysis of business cycles:  

 *  Production, growth and business cycles: I. The basic neoclassical model.  Journal of Monetary Economics (1988) 21:196-232. 
 *  Production, growth and business cycles: II. New directions.  Journal of Monetary Economics. (1988) 21:309-41. 
 *  Production, growth and business cycles: Technical Appendix.  Computational Economics (2002) 20: 87–116. 

CONTENTS OF THIS REPOSITORY:

* 'uhlig_solver_abreviated.ipynb'  Uhlig's solver algorithm using the generalized eigenvalue eigenvector method

* 'uhlig_solver_QZ.ipynb'  Uhlig's solver algorithm using a QZ decomposition as developed by:

  * Chris Sims in "Solving Linear Rational Expectations Models," Computational Economics, October 2002, Vol 20, Issue 1-2, pp 1-20, and in his MATLAB code qzdiv.m and qzswitch.m.  For more of Sim's work see http://www.princeton.edu/~sims/  
  
  * Paul Klein "Using the Generalized Schur Form to Solve a Multivariate Linear Rational Expectations Model,"  Journal of Economic Dynamics and Control, 24 (2000) 405-1423.  For more of Klein's work see  http://paulklein.ca/newsite/codes/codes.php  
  
  * The functions qzdiv() and qzswitch() are adaptations from Sims' MATLAB code into Python made by Kerk Phillips (https://github.com/kerkphil) and Yulong Li (https://github.com/yulong-git).

* Other programs:  Calc_Moments.ipynb, Detrend_Filters.ipynb, uhlig_impulse_resp_all.ipynb, uhlig_plot_impresp_all.ipynb, uhlig_simul_rand.ipynb, uhlig_plot_simul_all.ipynb

* Unsolved examples:  uhlig_example_xx.ipynb

* Solved examples with impulse responses:  za_impresp_example_xx.ipynb

* Solved examples with simulations, given randomly generated innovations:  zb_simul_example_xx.ipynb

* Solved examples filtered into trend and cyclical components with calculated moments for cyclical components:  zc_detmom_example_xx.ipynb 

* Solved examples using a QZ decomposition:  zd_qzsoln_example_xx.ipynb

COPYRIGHT:

(c) Harald Uhlig "Feel free to copy, modify and use at your own risk.  However, you are not allowed to sell this software or otherwise impinge on its free distribution."

NOTES:

Generalized Eigenvalue Eigenvector Method:

* As a check, I ran the examples using both my Python code and Uhlig's MATLAB code. I then compared the output matrices, i.e. PP, QQ, RR, SS, Resp_mat, and verified that these are identical for all models.  
* I also compared intermediate matrices, including Psi_mat, Gamma_mat, Theta_mat, Xi_mat, Delta_mat, Lambda_mat, Omega_mat, which are nearly identical for all models.  
* Exceptions occur in the intermediate matrices eVecs (Xi_eigvec) and eVals (Xi_eigval) because eigenvalues and eigenvectors computed in Python (numpy.linalg.eig() function) do not always coincide with MATLAB (eig() function). However, the results of both Python and MATLAB eigenvalue and eigenvector computations appear to be true and differences are not due to discrepancies in precision. 
* These differences have no impact on the solution output of examples 00, 01, 02, 03, 04_01, 04_02, 05_01, 05_02, 06 and 07. 
* In contrast, they do result in different intermediate and output matrices for 'Model 3 with Sunspots' of example 05.  Separately, for instructional purposes, Uhlig set-up 'Model 3' of example 04 incorrectly and the model hangs when solved. He showed the correction in example 05_03. 

QZ Decomposition:

*  When using MATLAB,  all examples have identical solution results for the generalized method and the QZ decomposition.
*  For the most part, the QZ decomposition in Python yields identical results to the QZ decomposition in MATLAB.
*  However, the functions numpy.linalg.qz() in Python and qz() in MATLAB return small discrepancies in the intermediate matrices in  examples 03, 04_01, 05_02 and 07.  But these are small enough so that the final output matrices are the same.
*  In example 05_03, however, both intermediate matrices and final output matrices are noticeably different between the Python and MATLAB QZ decomposition solvers.

Moment Calculations were spot checked against EViews.



