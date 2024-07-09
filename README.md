# esm2-antibody-CLIP
Multimodal training of ESM2 model for Antibody structural awareness.

# Introuction
OpenAI's CLIP model is quite impressive at connecting text with images, efficiently learning visual concepts from natural language supervision. Can we do the same for protein sequences and structure? Instead of text and images, we're integrating protein sequences with their structural information.

In a series of four accessible notebooks we develop a multimodal training approach that integrates antibody sequence data with structural data using a contrastive learning framework inspired by OpenAI's CLIP. We utilize the ESM2 model from Facebook's Evolutionary Scale Modeling (ESM) suite as our base architecture. The model was fine-tuned with a custom head for contrastive learning, where the sequence and structural embeddings were projected into a common latent space. Our training process focused on minimizing the contrastive loss to ensure that sequences and their corresponding structures were closely aligned in this space. We called this model ESM2-Ab-CLIP. 

We also evaluate the effect of ESM2-Ab-CLIP model on antibody binding affinity prediction task relative to the base ESM2 model. With ample data for fine-tuning, there were no additional benefits of multimodal training. However, the true strength of the ESM2AbCLIP model emerged under a low data regime. In this scenario, the ESM2AbCLIP model outperformed the base ESM2 model, on antibody binding affinity task as measured by spearmanr and Top 10% recall.


| Notebook | Keywords                           |
|--------|-------------------------------------------------------------------------------------|
| [SAbDab_ProteinFlow.ipynb](https://github.com/arjan-hada/esm2-antibody-CLIP/blob/main/ESM2_Ab_CLIP.ipynb) | Obtain antibody sequence and structure from Structural Antibody Database, perform MMSeqs2 clustering and generate Train/Valid/Test set.|
| [ESM_IF1_embeddings.ipynb](https://github.com/arjan-hada/esm2-antibody-CLIP/blob/main/ESM_IF1_embeddings.ipynb) | Generate antibody structure embeddings using ESM-IF1 and convert PDB files to ESM-IF1 embeddings.|
| [ESM2_Ab_CLIP.ipynb](https://github.com/arjan-hada/esm2-antibody-CLIP/blob/main/ESM2_Ab_CLIP.ipynb) | Perform multimodal training of ESM2, learning a joint embedding space of antibody sequence and structure.|
| [ESM2AbCLIP_bindaff_pred.ipynb](https://github.com/arjan-hada/esm2-antibody-CLIP/blob/main/ESM2_Ab_CLIP.ipynb) | Evaluate the effect of multimodal training on antibody binding affinity prediction.|

