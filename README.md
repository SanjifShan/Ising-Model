# Ising_Model

<img src="https://github.com/SanjifShan/Ising_Model/blob/main/ising_model.gif" width="250" height="250"/>

The Ising model in statistical mechanics is used to model phase transitions.

We will apply the Ising model to simulate interactions between spins in a symmetric lattice. Each node can occupy 2 possible spin states: +1 and -1.

We start with the Hamiltionian of the system. The energy of the system is given by:

<a href="https://www.codecogs.com/eqnedit.php?latex=E=&space;-&space;\sum_i&space;h_i&space;S_i&space;-&space;\sum_{i&space;\neq&space;j}&space;J_{ij}&space;S_i&space;S_j" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E=&space;-&space;\sum_i&space;h_i&space;S_i&space;-&space;\sum_{i&space;\neq&space;j}&space;J_{ij}&space;S_i&space;S_j" title="E= - \sum_i h_i S_i - \sum_{i \neq j} J_{ij} S_i S_j" /></a>

The first term is the contribution due to the interactions of all spins with an external magnetic field. If uniform, h is a constant.

J is analagous to the inertia matrix in classical mechanics. It describes the interactions of all spins with each other. We will use special cases of J to make things simpler.

In particular we could introduce a structure in a 2D system such that each spin is only affected by its nearest neighbours. So each spin can only interact with a maximum of 4 other spins(edge cases). This makes things way simpler.

In addition, since the lattice is isotropic and regular, the ineraction between spins for each spin is equal. This symmetry allows us to view J as a constant.

## Markov Chain Monte Carlo (MCMC)

We know each spins state depends only on the 4 neighbouring spins.

Thus, we can model this as a 2d markov chain. A 1d markov chain would have each spin only depend on 2 spins, the left and right.

We hope to estimate the probability of a spin or the expected number of spins given initial conditions (temperature) switching using a monte carlo simulation. 

A monte carlo simulation hopes to provide a reasonable picture of the probability distribution using a set of 'tries'. It works on th principle that the distribution of a large enough sample represents the actual population distribution (look up the Central Limit Theorem).


## Metropolis-Hastings Algorithm

Metropolis-Hastings

we use the metropolis hastings algorithm at a specific temperature and hope to estimate the expected value of spin states, and therefore energy and magnetisation.

The algorithm works as follows:

    1) Pick a random spin
    2) If switching the spin makes the system more stable (decreases energy), we switch.
    3) If switching the spin increases the energy, we do not immediately reject the posibility of switching. we compare it to a unform distribution. A sample of the uniform distribution 'represents' J, the interaction coefficient and if the change in energy is less that the sample, we switch. Note that other probability distributions can be used.
    4) Repeat until we have a reasonable prediction of the quantities we want.
    

