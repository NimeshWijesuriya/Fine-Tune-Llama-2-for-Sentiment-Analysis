# Fine-Tuning LLaMA 2 for Sentiment Analysis

## Overview

This project involves fine-tuning the LLaMA 2 model for sentiment analysis. The model was trained using a dataset imported from Hugging Face. Due to runtime and resource limitations on Google Colab, adjustments were made to the training process.

## Use Case

The primary goal of this project is to fine-tune a pre-trained LLaMA 2 model to classify sentiment in text data.

## Dataset

- **Training Data**: 2,000 records selected from a larger dataset to fit within runtime constraints.
- **Testing Data**: Imported from Hugging Face to validate the model's performance.

## Colab Runtime and Resource Constraints

- **Training Duration**: Due to Google Colab's free tier 90-minute runtime limit, the training was conducted with only 1 epoch to avoid exceeding the runtime and crashing the session.
- **Data Size**: A subset of the dataset (2,000 records) was used to ensure that the processing time remained within the allowable limits. Using the entire dataset caused the T4 GPU’s RAM to exceed its capacity and crash the session.
- **Session Renewal**: If the runtime exceeds the limit, the session needs to be renewed after 12 hours. This limitation further impacts the ability to use the entire dataset in a single training session.

## Model Fine-Tuning

The fine-tuning process includes the use of advanced techniques to efficiently adapt the model:

- **LoRA (Low-Rank Adaptation)**: LoRA is used to adapt pre-trained models by injecting trainable low-rank matrices into the model's layers. This allows for efficient fine-tuning with fewer parameters. Key parameters for LoRA include `lora_alpha`, `lora_dropout`, and `r`.
  
- **PEFT (Parameter-Efficient Fine-Tuning)**: PEFT methods are employed to fine-tune models efficiently by updating a smaller subset of parameters or applying specific adaptation techniques. In this project, LoRA is applied using PEFT to adapt the LLaMA 2 model.


