# Uhlig_Toolkit_in_Python

A Simple Toolkit for Computational Analysis: Solving linear approximations of dynamic stochastic general equilibrium (DSGE) models in Python

An abbreviated translation from MATLAB into Python of Harald Uhlig's solution method, as described in "A Tooklit for Analyzing Nonlinear Dynamic Stochastic Models Easily," Discussion Paper 101, Federal Reserve Bank of Minneapolis, June 1995 and in his MATLAB code. 

For more on Uhlig's toolkit see  https://www.wiwi.hu-berlin.de/de/professuren/vwl/wipo/research/MATLAB_Toolkit


CONTENTS OF THIS REPOSITORY:

'uhlig_solver_abreviated.ipynb'  Uhlig's solver algorithm using generalized eigenvalue method

Other programs:  Detrend_Filters.ipynb, uhlig_impulse_resp_all.ipynb, uhlig_plot_impresp_all.ipynb, uhlig_simul_rand.ipynb, uhlig_plot_simul_all.ipynb

Unsolved examples:  uhlig_example_xx.ipynb

Solved examples with impulse responses:  za_impresp_example_xx.ipynb

Solved examples with simulations based on randomly generated innovations:  zb_simul_example_xx.ipynb


NOTE:

As a check before uploading to this repository, I ran the example models using both my Python code and Uhlig's MATLAB code. I then  compared, not only output matrices and graphs, but also intermediate matrices.  Best as I can tell, these are identical for all models.  That said, I am aware that there maybe discrepancies between the eigenvalues and eigenvectors computed by Python compared to MATLAB. 

