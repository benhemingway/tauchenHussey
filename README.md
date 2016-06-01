# Tauchen-Hussey Discretization of an AR(1)


This function computes a n-dimensional discrete approximation to the AR(1) Auto Regressive Stochastic Process:

    y_t = (1-rho)*mmu + rho*y_{t-1} + epsilon_t
  
where epsilon is normally distributed mean 0 and standard deviation sigma. This is done using Tauchen and Hussey (1991)'s algorithm in Julia.

Note: you need the Distributions package.  If you don't already have it, install it by

    Pkg.add("Distributions")
Load the package and the function provided here:

    using Distributions
    include("tauchenHussey.jl")

Then, to use this function with a zero mean AR(1) (mmu = 0) with an n-dimensional discretization:

    y,transition = tauchenHussey(n,rho,sigma)

If you want the process to have a mean different from zero for a normal distrubution, map your mmu = mean/(1-rho).

    y,transition = tauchenHussey(n,rho,sigma,mmu = avg)

Since this is intended to map a normal distribution AR(1) process, to make it follow a log normal distribution with mean mmu, you need to take the exponential of the nodes:

    y = exp(y)


This code is a translation of the code by Martin Floden of Stockholm School of Economics. I have removed the baseSigma assignment as most people would use the default, but do change the code if it fits your needs. It can be found in: http://www2.hhs.se/personal/floden/CODE/tauchenhussey.m (Note that it has a mistake in the gausshermite loop (floor function has wrong parentheses).
