# ECC-lipids

ECC-lipids is a classical MD lipid force field with 
implicit embedding of the electronic polarization
through the Electronic Continuum Correction ([ECC](https://jmelcr.github.io/blog/ECC-post)).

The electronic polarization
(included e.g. via ECC)
is [important for accurate interactions](https://www.frontiersin.org/articles/10.3389/fmolb.2019.00143/full) 
of charged molecules, cation and anions, 
like sodium or [divalent calcium cations](http://aip.scitation.org/doi/10.1063/1.5006779),
as well as for overall neutral molecules 
like zwitterionic lipids, e.g. [POPC](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12510). 

This work is open to any contribution from anyone
from pointig out bugs, [raising issues](https://github.com/jmelcr/ecc_lipids/issues)
and adding extra starting structures 
to adding new molecules and headgroup-tail combinations and improving the whole force field.
Enjoy the force field, fork this repository 
and contribute through [pull requests](https://github.com/jmelcr/ecc_lipids/pulls)!


# Quick start

Good news - using ECC-lipids in your simulations is easy! 
Depending on naming conventions in coordinat files and topologies, 
we present two kinds of topologies:
 - CHARMM-compatible
 - AMBER-compatible

### CHARMM-compatible topologies

All topologies available in this repository at [ecc_lipids/topologies/ecc-lipids/](https://github.com/jmelcr/ecc_lipids/tree/master/topologies/ecc-lipids).

Some starting structures:
 - [POPC bilayer ](https://zenodo.org/record/1118266/files/sim_ECC-POPC_SPCE_noIons-ref.gro?download=1) (SPC/E water, 4 CaCl2, equilibrated)
 - [POPS bilayer ](https://zenodo.org/record/1488094/files/ECClipids_purePOPS_298K.gro?download=1) (SPC/E water, ECC-ions NaCl counterions, equilibrated)
 - [POPC:POPS (10:1) bilayer ](https://zenodo.org/record/1488094/files/ECClipids_10PC-1PS-mix_298K.gro?download=1) (SPC/E water, ECC-ions NaCl counterions, equilibrated)
 - [POPC:POPS (1:1) bilayer ](https://zenodo.org/record/1488094/files/ECClipids_1PC-1PS_mix_SPCE_298K.gro?download=1) (SPC/E water, ECC-ions NaCl counterions, equilibrated)
 - [POPC:POPS (4:1) bilayer ](https://zenodo.org/record/1488094/files/ECClipids_4PC-1PS-mix_298K.gro?download=1) (SPC/E water, ECC-ions NaCl counterions, equilibrated)
 - [POPC:POPS (5:1) bilayer ](https://zenodo.org/record/1488094/files/ECClipids_5PC-1PS-mix_298K.gro?download=1) (SPC/E water, ECC-ions NaCl counterions, equilibrated)
 - [POPC:POPS (5:1) bilayer ](https://zenodo.org/record/1488094/files/ECClipids_5PC-1PS-mix_298K_KCl.gro?download=1) (SPC/E water, ECC-ions KCl counterions, equilibrated)

Zenodo deposits including more details, e.g. long trajectories, salt concentrations, tested water models, simulation settings ... :
 - POPC and POPS lipid bilayers (various mixtures) and Na+ (K+) counterions - [Zenodo deposit](https://doi.org/10.5281/zenodo.1488093)
 - POPC and POPS lipid bilayers (various mixtures) and Na+ (K+) counterions and additional CaCl2 concentrations - [Zenodo deposit](https://doi.org/10.5281/zenodo.1488101)

**Can use CHARMM-gui!**
Also, since the molecular topology of ECC-lipdis 
is designed to agree with CHARMM lipids,
ECC-lipids can be used directly 
with the membrane structures generated by 
[CHARMM-gui.](http://charmm-gui.org/)
after changing only topology files (GROMACS format only). 
An example topology for ECC-lipids is given in 
[topologies/ecc-lipids](https://github.com/jmelcr/ecc_lipids/tree/master/topologies/ecc-lipids).

**Too lazy to make an initial structure?**
Already equilibrated CHARMM structures can be also downloaded 
from the [lipid membrane simulation database](http://www.nmrlipids.fi/) 
generated by the [NMRlipids project](http://nmrlipids.blogspot.com/),
and also by searching [Zenodo](https://zenodo.org/). 


### Amber Lipid14-compatible topologies

 - [POPC bilayer without ions and 3-point water model (SPC/E)](https://zenodo.org/record/1118266/files/sim_ECC-POPC_SPCE_noIons-ref.gro?download=1)
 - [POPC bilayer without ions and 4-point water model (TIP4p-2005)](https://zenodo.org/record/1118980/files/sim_ECC-POPC_TIP4p2005_noIons-ref.gro?download=1)
 - Simulations of POPC lipid bilayer in water solution at various NaCl and CaCl2 concentrations - [Zenodo deposit with SPC/E water model](https://doi.org/10.5281/zenodo.1118265)
 - Simulations of POPC lipid bilayer in water solution at various NaCl and CaCl2 concentrations - [Zenodo deposit with various water models](https://doi.org/10.5281/zenodo.1118979)

If you require Amber-like topology, you can use AmberTools to
make bilayers for Lipid14 and use the ECC-lipidds topology with
the Amber-like conventions, 
e.g. [Amber-like ECC-POPC](https://github.com/jmelcr/ecc_lipids/blob/master/topologies/ecc-lipids/ecc-popc/ECC-POPC_amber-lipid14-atomic-names.itp). 
The difference between the Amber-like resp. CHARMM-like
topologies are only in the atomic naming and ordering conventions, and
they generate identical results. 


## Which water model?

This is always a tricky question. 
For ECC-lipids, we have chosen the SPC/E water model as the standard, 
as it is consistent with the principles underling ECC.
However, the results with ECC-lipids are robust with respect to the choice of the water model
as was shown in [SI of ECC-POPC publication](https://pubs.acs.org/doi/suppl/10.1021/acs.jpcb.7b12510/suppl_file/jp7b12510_si_001.pdf). 

## papers with ECC-lipids

+ Accurate Binding of Sodium and Calcium to a POPC Bilayer by Effective Inclusion of Electronic Polarization, [ECC-POPC](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12510) also available at [GitHub](https://github.com/ohsOllila/NMRlipids_VI-NewIonModel)
+ Improved Cation Binding to Lipid Bilayers with Negatively Charged POPS by Effective Inclusion of Electronic Polarization [ECC-POPS](https://pubs.acs.org/doi/10.1021/acs.jctc.9b00824) also available at [GitHub](https://github.com/jmelcr/ecc_pops)


## related work

+ [NMRLipids projects](https://nmrlipids.blogspot.cz/)
   + [Molecular electrometer and binding of cations to phospholipid bilayers](https://pubs.rsc.org/en/content/articlelanding/2016/cp/c6cp04883h#!), also on [GitHub](https://github.com/NMRLipids/lipid_ionINTERACTION/blob/master/Manuscript/LIPIDionINTERACT.pdf) 
   + [Headgroup Structure and Cation Binding in Phosphatidylserine Lipid Bilayers](https://doi.org/10.1021/acs.jpcb.9b06091), also on [GitHub](https://github.com/NMRLipids/NMRlipidsIVotherHGs/blob/master/Manuscript/manuscriptPS.pdf) 

+ [Charge scaling manifesto](https://pubs.acs.org/doi/10.1021/acs.jpclett.9b02652)

+ [Accurate Biomolecular Simulations Account for Electronic Polarization](https://www.frontiersin.org/articles/10.3389/fmolb.2019.00143/full) 

+ Molecular dynamics in electronic continuum (MDEC)
   + MDEC 2009, [Electronic continuum model for molecular dynamics simulations](http://scitation.aip.org/content/aip/journal/jcp/130/8/10.1063/1.3060164)
   + MDEC 2010,
## pre-equilibrated ECC-lipids membranes 

 [Electronic Continuum Model for Molecular Dynamics Simulations of Biological Molecules](http://dx.doi.org/10.1021/ct9005807)


## notes

The directory structure and working style of this repository
is highly inspired by open-collaboration [NMRLipids projects](https://nmrlipids.blogspot.cz/),
with its [GitHub repositories](https://github.com/NMRLipids).

Repository [MATCH](https://github.com/NMRLipids/MATCH) is often also employed 
as a data source and a tool with analysis scripts.

Gromacs compatible parameters for ECC-ions (and many other ions)
are maintained at a [separate repository.](https://bitbucket.org/hseara/ions) 
