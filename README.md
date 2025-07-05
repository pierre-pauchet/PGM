# Expanding Not-MIWAE – Experiments on Not-MIWAE

## Project Outline

In this project, realised in collaboration with [Laura Choquet](https://github.com/lauraachoquett), we expand on an existing generation framework to infer missing data in complex real-world scenarios.  
The original paper [(Ipsen, Mattei, Frellsen, 2020)](https://arxiv.org/abs/2006.12871) introduces a new autoencoder model specialized in reconstructing data with a missing pattern dependent on the value of the missing data itself.  
This peculiar missing pattern is known as **Not Missing At Random (NMAR)**, as opposed to **Missing At Random (MAR)**, which may depend on the observed data but not the missing one.

This project was conducted in the context of the class *Probabilistic Graphical Models*, taught by P. Latouche and P.A. Mattei as part of the **MVA Masters Degree**.  
We obtained the grade of *17/20 (4.0+/4.0)*. I am grateful to my classmate Laura Choquet for our collaboration, and to the professors for their great teaching material.
## Key findings

- **Improved performance** with masked not-MIWAE  :

We added a latent mask variable, modifying the original learning objective of the model but allowing it to infer the morphology of the missing data directly in the latent space. We show a **~5% improvement in RMSE inferrence of missing data** compared to baseline not-MIWAE in multiple experimental settings. 
- **Joint supervision** shows limitations :

Our hypothesis was the following : could the not-MIWAE model reconstruct missing data better if its inferred data was used to train a supervised-learning model, with both models sharing a **joint training objective ?**

In out experiments, we trained a simple MLP regressor on values inferred by not-MIWAE, with both the VAE and the MLP learning simultaneously. We **could not show significant performance improvements** in our experiments. However, the theoretical framework we devised is mathematically valid, and we believe improvements could be reached with better training and other supervised learning tasks/more complex models. 

---

<p align="center">
  <img src="Poster_PGM_Choquet_Pauchet.jpg" alt="Poster" width="600">
</p>



## Code and experiments

This repo contains the Jupyter notebooks we used to generate our graphs and results, for reproducibility. Please note that the code is not optimised and not meant to be ran as it stands. We encourage you to refer to the [original code from the authors](https://github.com/nbip/notMIWAE) for a cleaner, standalone version. 

You can also check [our report](PGM_report_Choquet_Pauchet_notMIWAE.pdf) for more detail on our experimental setup and mathematical background for our work. All of the interesting graphs and tables are available there, and it might be a quicker read. 

## Contact 

If you have any question, feel free to contact me on Linkedin or by email : pierre.pauchet at_sign etu.u-paris.fr