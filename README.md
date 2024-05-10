# mlhc-24
Student project on evaluating bias in open source LLMs along with considering adversarial attacks. Experiment was conducted on Google Cloud Platform's Colab Enterprise using 1 NVIDIA L4 GPU.


Below is the step-by-step to reproduce results:

1) Access an open-source LLM via hugging face: https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2; this can be downloaded and uploaded into GCP storage to avoid running out of storage for your runtime
2) Run the mlhc_synthetic_generation notebook to create scenarios of low and high risk patient symptoms and medical tests
3) Run the mlhc_data_extraction notebook to extract patient symptoms and medical tests
4) Reconstruct a new prompt using the extracted features. Replicate the same reconstructed prompts adding only one piece of demographic information. This was done in Excel, but easily done in Python as well.
5) Run the mlhc_fine_tuning_baseline notebook to train the first triage classifier
6) Run the logit_extraction notebook to calculate logits for the evaluation of test set
7) Run the same process for adversarial training using the adversarial notebook
8) Calculate logits for that evaluation
9) Run mlhc_viz to compute graphs

Note these steps are subject to change as data generation formatting is subject to change which requires modifications to 3 and 4. 
