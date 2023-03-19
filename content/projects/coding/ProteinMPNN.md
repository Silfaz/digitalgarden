---
title: "ProteinMPNN"
---

This model takes as **input a protein structure** and based on its backbone **predicts new sequences** that will fold into that backbone. Optionally, you can then run AlphaFold2 on the predicted sequence to check whether the predicted sequences adopt the same backbone (WIP).


![](projects/attachments/Pasted%20image%2020230128162327.png)
https://huggingface.co/spaces/simonduerr/ProteinMPNN

Colab notebook to run MPNN and then Alphafold on the output: https://colab.research.google.com/github/sokrypton/ColabDesign/blob/v1.1.0/mpnn/examples/proteinmpnn_in_jax.ipynb#scrollTo=GjdIxO4j-Hnn

https://colab.research.google.com/github/sokrypton/ColabDesign/blob/v1.1.0/mpnn/examples/proteinmpnn_in_jax.ipynb

