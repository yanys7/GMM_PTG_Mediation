Compilation environment:

    Intel® Parallel Studio XE Cluster Edition for Linux

To compile:

    source set_env.sh

    mkdir build

    cd build

    cmake ..

    make

To run the program for high-dimensional mediation analysis:

    ./bin/mcmc_rd.x n c1 c2 q burnIn iter 1 1 Y_file M_file A_file C1_file C2_file beta_m.ini_file alpha_a.ini_file pi_m.ini_file pi_a.ini_file

where
n = sample size

c1 = number of covariates in the outcome model

c2 = number of covariates in the mediator model

q = number of mediators

burnIn = iterations for burnIn

iter = total number of iterations

A_file = exposure file containing n-by-1 exposure vector

M_file = mediators file containing n-by-q matrix

Y_file = outcome file containing n-by-1 outcome vector

C1_file = covariate file containing n-by-c1 covariate matrix for the outcome model, with the first column being 1 for the intercept

C2_file = covariate file containing n-by-c2 covariate matrix for the mediator model, with the first column being 1 for the intercept

beta_m.ini_file = initial values for 1-by-q beta_m vector (mediator-outcome coefficients) in the outcome model, 

alpha_a.ini_file = initial values for 1-by-q alpha_a vector (exposure-mediator coefficients) in the mediator model

pi_m.ini_file = initial values for pi_m, the proportion of non-zero elements in beta_m

pi_a.ini_file = initial values for pi_a, the proportion of non-zero elements in alpha_a

Please make sure there is no missing or NA values in the above files.

The output file is 'results_11.txt', which contains the posterior samples of (beta_mj, r1j, alpha_aj, r3j) for each j-th mediator. Then follows the posterior samples of pi_m, pi_a, beta_a, sigma_m0, sigma_m1, sigma_ma0, sigma_ma1.

The posterior inclusion probability of each mediator is P(r1j = r3j = 1 | Data), which can be obtained from the posterior samples.
