Compilation environment:

    Intel® Parallel Studio XE Cluster Edition for Linux

To compile:

    source set_env.sh

    mkdir build

    cd build

    cmake ..

    make

To run the GMM for high-dimensional mediation analysis:

    ./bin/mcmc_rd.x n c1 c2 q burnIn iter 1 1 Y_file M_file A_file C1_file C2_file beta_m.ini_file alpha_a.ini_file pi.ini_file Cov_file

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

pi.ini_file = initial values for pi, the proportions of the four Gaussian components

Cov_file = the scale matrix (2-by-2) in the Inverse-wishart prior

Please make sure there is no missing or NA values in the above files.

One output file is 'probs_gmm_11.txt', which contains the posterior samples of (pi_1, pi_2, pi_3, pi_4) for each j-th mediator, stacked in order. The posterior pi_1 is the posterior inclusion probability.

Another output file is 'results_gmm_11.txt', which contains the posterior samples of (beta_mj, alpha_aj, r_j) for each j-th mediator, stacked in order. 

To run the PTN for high-dimensional mediation analysis:

    ./bin/mcmc_PTN_rd.x n c1 c2 q burnIn iter 1 1 l01 l11 l21 Y_file M_file A_file C1_file C2_file beta_m.ini_file alpha_a.ini_file Cov_file

where
n = sample size

c1 = number of covariates in the outcome model

c2 = number of covariates in the mediator model

q = number of mediators

burnIn = iterations for burnIn

iter = total number of iterations

l01 = lambda_0; l11 = lambda_1; l21 = lambda_2

A_file = exposure file containing n-by-1 exposure vector

M_file = mediators file containing n-by-q matrix

Y_file = outcome file containing n-by-1 outcome vector

C1_file = covariate file containing n-by-c1 covariate matrix for the outcome model, with the first column being 1 for the intercept

C2_file = covariate file containing n-by-c2 covariate matrix for the mediator model, with the first column being 1 for the intercept

beta_m.ini_file = initial values for 1-by-q beta_m vector (mediator-outcome coefficients) in the outcome model

alpha_a.ini_file = initial values for 1-by-q alpha_a vector (exposure-mediator coefficients) in the mediator model

Cov_file = the rate parameters (2-by-1) in the Inverse-Gamma priors for the variances of the unthresholded beta_m and alpha_a. Both of the shape parameters are set to be 1.1

The output file is 'results_11.txt', which contains the posterior samples of (beta_mj, alpha_aj, r1_j, r2_j) for each j-th mediator, stacked in order, r1_j indicates whether beta_mj is non-zero, r2_j indicates whether alpha_aj is non-zero. The following columns contain the posterior samples of beta_a, sigma_e, sigma_g, and the loglikelihood.

