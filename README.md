# BIOMD0000000090: Wolf2001_Respiratory_Oscillations

## Installation

Download this repository, and install with distutils

`python setup.py install`

Or, install using pip

`pip install git+https://github.com/biomodels/BIOMD0000000090.git`

To install a specific version (in this example, from the 2014-09-16 BioModels release)

`pip install git+https://github.com/biomodels/BIOMD0000000090.git@20140916`


# Model Notes


This model by Jana Wolf et al. 2001 is the first mechanistic model of
respiratory oscillations in Saccharomyces cerevisae. It is based on the
assumption that feedback inhibition of cysteine on the sulfate transporters
leads to oscillations in this pathway and causes oscillations in respiratory
activity via inhibition of cytochrome c oxidase by hydrogen disulfide. The
model is qualitative/semi-quantitative and reproduces the respiratory
oscillation pattern quite well. It is based on very coarse-grained
representations of the mitochondrial tricarboxylic acid cycle and the
mitochondrial electron transport chain (oxidative phosphorylation). The
sulfate assimilatory pathways also contains some significant simplifcations.

The model corresponds to Fig. 2B of the paper, with a slight phase shift of
the oscillations. No initial conditions were given in the paper, and thus they
were chosen arbitrarily in a range that lies within the basin of attraction of
the limit cycle oscillations. Species IDs correspond to IDs used by the
authors, while SBML names are more common abbreviations.

Caveats:  
1) Equilibrated transport:  
The model assumes fast equilibration between mitochondria and cytoplasm for
the metabolites NADH, NAD+, H2S and Acetyl-CoA.  
2) Cytosolic mass conservation ATP/ADP:  
The model uses mass conservation for cytosolic adenosine nucleotides with is
however not encoded in the stoichiometry, but is implied by the lumped
reaction v4. This reaction combines the enzymatic reactions of
phosphoadenylyl-sulfate reductase (thioredoxin) (yeast protein Met16p, EC
1.8.4.8) and sulfite reductase (NADPH) (subunits Met5p and Met10p, EC
1.8.1.2). EC 1.8.4.8 also has adenosine-3',5'-bismonophosphate (PAP, not to
confuse with ID pap in this model, standing for PAPS) as a product. PAP is the
substrate for enzyme 3'(2'),5'-bisphosphate nucleotidase (Met22p, EC:3.1.3.7)
which would revover AMP (and Pi). Then AMP can be assumed to be equilibrated
with ATP and ADP via adenylate kinase, as often used in metabolic models. This
AMP production is implied in the mass conservation for cytosolic adenosine
phosphates. Accounting for these reactions explicitly does not change the
dynamics of the model significantly. An according version can be obtained from
the SBML creator (Rainer Machne, mailto:raim@tbi.univie.ac.at).  
3) Redox balance:  
The enzyme sulfite reductase (NADPH) (subunits Met5p and Met10p, EC 1.8.1.2,
part of reaction v4) actually uses NADPH, and the authors assume equilibration
of NADH and NADPH. But actually S. cerevisiae specifically is missing the
according enzyme transhydrogenase (EC 1.6.1.1 or EC 1.6.1.2). EC 1.8.4.8 also
oxidizes thioredoxin and would actually require an additional NADPH for
thioredoxin recovery (reduction). This would slightly affect the redox balance
of the model.  
4) Energy balance:  
Reaction v7 lumps NAD-dependent alcohol dehydrogenase (EC 1.1.1.1), aldehyde
dehydrogenase (NAD+) (EC 1.2.1.3) and acetyl-CoA synthase (EC 6.2.1.1). The
latter reaction would actually consume ATP as a co-factor, producing AMP+PPi,
and this is not included in the model. This would slightly bias the model's
energy balance.

  

To the extent possible under law, all copyright and related or neighbouring
rights to this encoded model have been dedicated to the public domain
worldwide. Please refer to [CC0 Public Domain
Dedication](http://creativecommons.org/publicdomain/zero/1.0/) for more
information.

In summary, you are entitled to use this encoded model in absolutely any
manner you deem suitable, verbatim, or with modification, alone or embedded it
in a larger context, redistribute it, commercially or not, in a restricted way
or not.

  

To cite BioModels Database, please use: [Li C, Donizelli M, Rodriguez N,
Dharuri H, Endler L, Chelliah V, Li L, He E, Henry A, Stefan MI, Snoep JL,
Hucka M, Le Novère N, Laibe C (2010) BioModels Database: An enhanced, curated
and annotated resource for published quantitative kinetic models. BMC Syst
Biol., 4:92.](http://www.ncbi.nlm.nih.gov/pubmed/20587024)


