# Tauchen-Hussey Discretization of an AR(1)
###################

	This function computes a discrete
	approximation to the AR(1) Auto Regressive Stochastic Process

	y_t = (1-rho)*mu + rho*y_{t-1} + epsilon_t
  
	where epsilon is normally distributed mean 0 and standard deviation sigma.
  This is done using Tauchen and Hussey (1991)'s algorithm.

  Note: you need the Distributions package.
  If you don't already have it, install it by
  Pkg.add("Distributions")
  Load it by:   using Distributions

  Inputs:
	n is the number of discrete points you want the approximation to use
  rho is the value of the persistance parameter
  sigma is the standard deviation of the innovation epsilon_t
  mmu is mean of AR(1) process. Defaults to zero mean

  Outputs:
  actualPoints: length n vector of the points of the Normal Distribution
  probabilities:  nxn matrix of transitions: entry   p_ij  tells you the probility of transitioning
					from state i to state j.

	Reference: http://www.fperri.net/TEACHING/macrotheory08/numerical.pdf
  
  This code is a translation of the code by Martin Floden of Stockholm School of Economics
  It can be found in: http://www2.hhs.se/personal/floden/CODE/tauchenhussey.m (Note that it has a mistake in the gausshermite loop (floor function)
###################
