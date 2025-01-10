# Boosting Generalization of Small Language Models for Medical Q/A Task

## Note
The repository contains code for fine-tuning the flan-t5-small model on two datasets: iCliniq Dataset and MedQuAD Dataset. For implementation details and our code for model merging techniques, please refer to the: [LLM-Merging Repository](https://github.com/DevChuriwala/LLM-Merging/tree/dev/llm-291).

## Abstract
This project enhances the performance of small language models (SLMs) for healthcare applications by employing advanced model merging strategies (Model Soup, SLERP, TIES, DARE, Task Arithmetic, and Weighted Average). It effectively addresses data privacy and resource constraints, facilitating the deployment of efficient medical Q&A systems on edge devices. The approach is validated through experiments conducted on the iCliniq and MedQuAD datasets.

## Problem
How can we overcome data privacy concerns and resource limitations to optimize language models for real-world healthcare applications?

## Importance
- **Data Accessibility Issues**: Privacy concerns limit access to healthcare datasets, which hampers model generalization.
- **Resource Demands**: Fine-tuning large language models is computationally expensive and requires significant resources.
- **Edge Computing Needs**: Efficient small models are crucial for deployment on edge devices, where computational power and memory are limited.

## Motivating Question
Can we enhance the generalization and performance of small language models (SLMs) to meet the specific needs of healthcare applications, particularly for deployment on edge computing devices?

## Methodology
To enhance the performance of small language models for medical Q&A tasks, we employed two main strategies:

1. **Fine-Tuning**: Utilizing resource-efficient techniques to optimize model performance:
   - **PEFT** (Parameter-Efficient Fine-Tuning)
     - **QLoRA** (Quantized Low-Rank Adaptation)

2. **Model Merging**: Combining multiple model outputs using advanced techniques to boost generalization and efficiency:
   - **Model Soup**: Combines multiple fine-tuned models by averaging their weights, resulting in a single model with improved performance across various tasks.
   - **SLERP (Spherical Linear Interpolation)**: Interpolates model weights in a spherical space, preserving the geometric structure of the weight space for smoother transitions between models.
   - **TIES (Trim, Elect, Sign & Merge)**: Optimizes task vectors by retaining the top-k% largest values, resolving sign conflicts, and averaging aligned parameters for integration with the original model.
   - **DARE (Drop and Rescale)**: Reduces redundancy by randomly dropping a large percentage of parameter updates, rescaling the remaining ones, and enhancing model integration with minimal performance loss.
   - **Task Arithmetic**: Combines task-specific models by integrating task vectors, which capture directional weight changes, improving multitask performance without the need for retraining.
