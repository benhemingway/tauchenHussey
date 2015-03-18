# Tauchen-Hussey Discretization of an AR(1)


This function computes a discrete approximation to the AR(1) Auto Regressive Stochastic Process

    y_t = (1-rho)*mu + rho*y_{t-1} + epsilon_t
  
where epsilon is normally distributed mean 0 and standard deviation sigma. This is done using Tauchen and Hussey (1991)'s algorithm.

Note: you need the Distributions package.  If you don't already have it, install it by

    Pkg.add("Distributions")
Load it by:

    using Distributions

This code is a translation of the code by Martin Floden of Stockholm School of Economics. It can be found in: http://www2.hhs.se/personal/floden/CODE/tauchenhussey.m (Note that it has a mistake in the gausshermite loop (floor function has wrong parentheses).

