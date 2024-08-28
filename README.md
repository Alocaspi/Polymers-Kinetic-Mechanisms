# Polymers-Kinetic-Mechanisms
![Logo](.images/intro.svg)

Condensed-phase polymer degradation kinetic Mechanisms. Evaluation of gas-phase
pyrolytic and gasification reactivity are underway at CRECK modelling POLIMI.
The present repository is the polymer pyrolysis subset of the comprehensive one
on GitHub of [Creck Modeling Lab](https://github.com/CRECKMODELING/Kinetic-Mechanisms).
The mechanisms reported here are those employed and validated for my [PhD Thesis](Locaspi_phdthesis.pdf).

The folders are organized by polymer type. In general semi-detailed, reduced, 
and multi-step mechanisms are available. Specifically:
- **Polyethylene** ([PE](PE)): different models are available for HDPE and LDPE
    according to the degree of detail involved in products and radicals description.
    For HDPE both [semi-detailed](PE/HDPE_semidetailed), [reduced](PE/HDPE_reduced) 
    and [multistep](PE/HDPE_multistep) versions are availble. The same holds for LDPE with
    the [semi-detailed](PE/LDPE_semidetailed), [reduced](PE/LDPE_reduced) and 
    [multistep](PE/LDPE_multistep) mechanisms are reported. Thermodynamics and transport
    have been assessed as well.
- **Polypropylene** ([PP](PP)): has a [semi-detailed](PP/PP_semidetailed), [reduced](PP/PP_reduced)
    and [multistep](PP/PP_multistep) mechanism available as well. Thermodynamics and transport
    have been validated. The mechanism for APP has not been reported due to the lower importance
    of APP in general wastes.
- **Polystyrene** ([PS](PS)): the proposed mechanisms account for all structural differences. 
    The [semi-detailed](PS/PS_semidetailed) mechanism and both a [reduced](PS/PS_reduced) 
    and [multistep](PS/PS_multistep) version are currently available with validated
    thermodynamic properties. 
- **Poly(ethylene terephthalate)** ([PET](PET)): a single semi-detailed [mechanism](PET) 
    accounts for the pure polymer degradation considering a single condensed pseudo-phase. Thermodynamic properties have NOT been studied.
- **Poly(vinyl chloride)** ([PVC](PVC)): the [mechanism](PVC) of [Marongiu et al. (2003)](https://doi.org/10.1016/S0165-2370(03)00024-X) 
    is here reported and employed for the pure polymer degradation. Thermodynamic properties have NOT been studied.
- Currently underway are models for **PA, PMMA, and PU** and condensed-phase interactions

## Experimental Data Availability
The folders of each polymer investigated report all the literature experimental data 
employed for validation purposes. For most mechanisms, some validation comparisons
are reported as well. I do not own any of these data, they are generally taken with
plot_digitizer from the of plots of published papers (so there is lots of rumor 
which hinders the quality of DTG comparisons).

In each polymer folder there is a subfolder labelled "Exp_data". This is composed
of subfolders labelled with the corresponding operating condition (e.g., 10 Kmin)
and containing a json file (Exp_data.json) with all the data inside. The data are
structured by type (TG, DTG, DSC, Gas_Yield), author, and values (with units). 
No DOI is reported herein, but you can find all the exact references on the 
mechanism papers. Gas yields data are already lumped to the models' species.

Each Exp_data folder also hosts a file "Operating_conditions.json", which reports
the information used for model simulation (e.g., how the temperature profiles are
estimated, and so on).

Experimental data on mixture pyrolysis and volatiles molar yields have not been 
yet placed here.

## Kinetic Mechanism Description
    
The aim of the proposed kinetic models is to reproduce the main features of the degradation
process at low computational cost. This refers to describing the characteristic
degradation times (mass-loss profiles), product distribution, and heat requirements.

The kinetic mechanism are of the semi-detailed or lumped kind employing a
functional group approach:
- Long polymer chains are described with functional groups characteristic of
    the polymer moieties (mid- and end-chain groups) recognized by the "P-" in
    their name
- Short chains, i.e. compounds of interest, are described with real species as
    C2H4, C15H30, etc

Thermochemistry has been validated for PE, PP, and PS.
Transport parameters are evaluated with a simplified approach based on critical
temperatures and pressures, see [Holley et al. (2009)](http://dx.doi.org/10.1016/j.proci.2008.05.067).
The present models cannot be directly coupled to the creck gas-phase mechanism, 
but further work is underway to assess the secondary gas-phase reactivity.

<img src=".images/aim.svg" width="10000" >

     

