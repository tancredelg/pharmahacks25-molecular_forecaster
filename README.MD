# PharmaHacks 2025  
## Challenge: Predict Kinase Selectivity Using Machine Learning  

### Repository Contents  

- **`all_seqs.pkl`**  
  A pickled version of all amino acid sequences for each kinase.  

- **`global_embeddings_max_length.npy`**  
  A NumPy array of the global embeddings for each amino acid sequence obtained with ProteinBert.  
  **Note:** Local embeddings are not included in this repository but can be obtained from the same model.  

- **`global_embeddings_map.pkl`**  
  A pickled version of the mapping between kinases and their respective global embeddings.  

- **`Table-1.xlsx`**  
  A table containing additional information about each kinase.  

- **`Table-2_train.xlsx`**  
  A table containing selectivity scores and SMILES strings for the training set.  

- **`Table-3_train.xlsx`**  
  A table of Kd values for the training set.
  **Note:** Some values were initally left blank as the dissociation constant was too high, and were replaced by the placeholder value 10001.

- **`starter_notebook.ipynb`**  
  A Jupyter notebook provided as an **example code** to help you get started with the challenge. 

### Submission Instructions  
- Put your **notebook** and **slides** in a **GitHub repository** and post it on [Devpost](https://pharmahacks-2025.devpost.com/?ref_feature=challenge&ref_medium=discover&_gl=1*oayv4s*_gcl_au*MTE2NjM0NTYwLjE3MzcyMTQ1NjI.*_ga*MTc5OTkxOTUxNS4xNzM3MjE0NTYy*_ga_0YHJK3Y10M*MTc0MTk5MjU5Ni4yOS4xLjE3NDE5OTUxNjAuMC4wLjA)


### Important Notes  

- You are **not required** to use `all_seqs.pkl`,`global_embeddings_max_length.npy` and `global_embeddings_map.pkl`; they are provided for **your convenience**.  
- The **test set will be released on Sunday at 11 AM**.
