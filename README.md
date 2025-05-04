# 🫁 Enhancing MEDCLIP with semantic disease label expansion 

This project fine-tunes the MedCLIP model (Vision Transformer-based) on the NIH ChestX-ray14 dataset using enriched disease labels. The label enrichment is achieved through SNOMED CT synonyms to improve  classification performance in a multi-label setting.

📁 *Dataset*
- NIH ChestX-ray14: A large-scale dataset containing 112,120 frontal chest X-ray images across 14 disease categories.

- Label Expansion: Original disease labels were expanded using SNOMED CT synonyms to generate multi-hot vectors representing each image's conditions.

🧠 *Model*
- Base Model: MedCLIP with a ViT (Vision Transformer) visual encoder.

- Modified Head: Classification head outputs 56 logits, corresponding to 70 labels (including synonyms) merged into 56 disease classes.

- Loss Function: BCEWithLogitsLoss compares predicted logits with synonym-expanded multi-hot label vectors.

🏋️‍♀️ *Training*
Training Strategy:

- Each image is passed through the encoder.

- The output logits are compared against the enriched label vector using BCEWithLogitsLoss.

- The model is trained using the Adam optimizer.

📊 *Metrics*

- Loss

- AUC (Area Under the ROC Curve)


📚 *References*

- MedCLIP: MedCLIP: Contrastive Learning from Unpaired Medical Images and Text by Z. Wang et al.
- NIH ChestX-ray14 Dataset
- SNOMED CT
