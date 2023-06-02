---
title: "Hackathon"
---


- What's our challenge
- Find receptor
- Find anything that binds to that receptor (ideally something that was experimentally proven to bind and work) --> which parts of the proteins dock to the receptor
- Alphafold2: give a sequence (.fasta), gives you a structure. Let it fold both amino acid sequences together. We can do this with various parts of the protein (e.g. if we don't find a paper about the active sites of the receptor or the ligand).
- Binder hallucinations: binding a target shorturl.at/hsxN8
- MPNN: from a pdb structure (.pdb) get a sequence shorturl.at/nwNVW. Can also autocomplete proteins or remove parts of the protein that should not be included (e.g. only look for active site). 
- Strategy: don't really change native protein but create a lot of different versions with different chemistries --> some of them will produce tastes that are different to the native.
- Inpainting roseTTAfold on git -  shorturl.at/glrA8
- Avoid disulfide bonds for the start
- Evaluation: 
	- The protein you designed with Rosettafold, put into Alphafold to fold --> will give confidence score --> align the two structures in Pymol
	- Fold receptor together with ligand in Pymol