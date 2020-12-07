# Diodes
Diodes are the most basic active electronic components. They are unidirectional semiconductors which only allow current to flow in one direction. Diodes are made from a single semiconductor strip (one NP split). 

Diodes are non-linear components and have an exponential IV relationship. 

## Rho (ρ)
Rho is defined as the resistivity metric for materials and is measured in ohm-meters (Ωm). Conductors, semiconductors and insulators are categorized by this metric. Notably, the distribution of resistivity across these categories is not uniform. This is due to the ambient temperature as metals are much better conductors of heat than insulators.

## Semiconductors
Semiconductors materials such as silicon (Si), germanium (Ge) and gallium arsenide (GaAs), have electrical properties between conductors and insulators. They are called intrinsic semiconductors since they are chemically pure semiconductors, and have very few “free electrons” because their atoms are closely grouped together in a crystal lattice but electrons are still able to flow, but only under special conditions. 

The ability of semiconductors to conduct electricity can be greatly improved by replacing or adding certain donor or acceptor atoms to this crystalline structure, producing more free electrons than holes or vice versa. This process of adding donor or acceptor atoms to semiconductor atoms (the order of 1 impurity atom per 10 million (or more) atoms of the semiconductor) is called Doping. The as the doped silicon is no longer pure, these donor and acceptor atoms are referred to as impurities, and by doping these silicon material with a sufficient number of impurities, we can turn it into an N-type or P-type semi-conductor material. Extrinsic semiconductors are doped with N-type or P-type impurities.

## N-Type Semi-conductors
N-type semi-conductors, are majority carriers with electron excess. These are materials which have pentavalent impurity atoms (donors) added and conduct by electron movement and are therefore called, N-type Semiconductors. Doping for an N-type semiconductor gives positively charged donors and negatively charged free electrons.
![img](/Components/img/NTYPE.png)

## P-Type Semi-conductors
P-type semi-conductors, are minority carriers with an excess of holes. These are materials which have trivalent impurity atoms (acceptors) added and conduct by hole movement and are therefore called, P-type Semiconductors. Doping for an P-type semiconductor gives negatively charged acceptors and positively charged free holes.
![img](/Components/img/PTYPE.png)

Both N and P-type semiconductors are electrically neutral on their own since in either case there is no sink potential for the excess electrons or holes to travel towards

# PN-Junction
As the N-type semiconductor and P-type semiconductor materials are fused, a very large density gradient exists between both sides of the PN junction. The result is that some of the free electrons from the donor impurity atoms begin to migrate across this newly formed junction to fill up the holes in the P-type material producing negative ions.

However, because the electrons have moved across the PN junction from the N-type silicon to the P-type silicon, they leave behind positively charged donor ions on the negative side and now the holes from the acceptor impurity migrate across the junction in the opposite direction into the region where there are large numbers of free electrons.

As a result, the charge density of the P-type along the junction is filled with negatively charged acceptor ions, and the charge density of the N-type along the junction becomes positive. This charge transfer of electrons and holes across the PN junction is known as diffusion. The width of these P and N layers depends on how heavily each side is doped with acceptor density, and donor density, respectively.
![img](/Components/img/PN-JUNC.png)


![img](/Components/img/operational-characteristics.png)

There are two operating regions and three biasing conditions for the standard junction diode and these are:
1. Zero Bias – No external voltage potential is applied to the PN junction diode.
2. Reverse Bias – The voltage potential is connected negative, (-ve) to the P-type material and positive, (+ve) to the N-type material across the diode which has the effect of Increasing the PN junction diode’s width.
3. Forward Bias – The voltage potential is connected positive, (+ve) to the P-type material and negative, (-ve) to the N-type material across the diode which has the effect of Decreasing the PN junction diodes width.