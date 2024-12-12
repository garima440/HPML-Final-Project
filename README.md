# HPML-Final-Project

# Efficient Fine Tuning and Inference Optimization for TinyBert

## GOALS / OBJECTIVES

This project focuses on enhancing the performance and
efficiency of TinyBERT, a pre-trained transformer-based
language model. The goal is to implement and compare
various techniques for fine-tuning TinyBERT effectively
while optimizing its inference speed, aiming to improve its
deployment capabilities on resource-constrained devices.s/
Objectives.


## APPROACH/TECHNIQUES

● Fine-tuning with LoRA: To improve the
fine-tuning process of TinyBERT by employing
Low-Rank Adaptation (LoRA), which allows for
efficient updates to the model parameters.

● Implementation of kv Caching: To optimize
inference speed by implementing key-value caching
mechanisms, allowing for more efficient attention
computations.

● Implementation of Weights & Biases Sweeps: for 
hyperparameter optimization using sweeps with the 
objective to maximize accuracy. 


● Model Quantization: To reduce the model's
memory footprint and improve inference speed
through quantization techniques without
significantly degrading performance.

● Flash Attention Integration: To utilize flash
attention mechanisms to accelerate attention
computations during training and inference.

● Profiling and Performance Analysis: To measure
and analyze the model's performance in terms of
speed, memory consumption, and efficiency gains
resulting from the aforementioned techniques.

## Dataset Overview

The Microsoft Research Paraphrase Corpus (MRPC) is one of the tasks in the GLUE Benchmark. It is designed to evaluate a model's ability to determine semantic equivalence between pairs of sentences. MRPC presents pairs of sentences extracted from online news sources and challenges the model to identify whether the sentences in each pair convey the same meaning.

Data Details
-------------
Dataset Source: Part of the GLUE benchmark, loaded using the Hugging Face datasets library.

Input Format: Sentence pairs (sentence1, sentence2).

Output Labels:

1: Sentences are semantically equivalent (paraphrase).

0: Sentences are not semantically equivalent.

Results and Conclusion
-------------
Accuracy Improvement:<br>
	•	The fine-tuned model achieves an accuracy improvement of 82.353% compared to the base model (from 63.73% to 82.35%). 
 
Latency Optimization:<br>
	•	Below image shows the improvement in the inference latency accross different batch sizes
![image](https://github.com/user-attachments/assets/3eef7899-7a9f-4f99-a189-bd6a284cc456)

 Model Size reduction: 21.19MB: <br>
        •	The fine-tuned model size is reduced from 54.74MB to 21.19MB leading to a reduction of 61.3% in model size.

 Trainable Parameters:
        •	After the application of LoRA, the number of trainable parameters decreased substantially from 14.35 million to 120,434, 
                leading to a reduction of 99% in the total parameters.

Larger batch size handling for Flash Attention:
        •  When we implemented Flash Attention, the model was able to handle larger batch sizes upto 2048 batches


## References

1. **LoRA: Low-Rank Adaptation of Large Language Models**  
   Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, Weizhu Chen.

2. **Inference Optimization for Large Language Models: Effects, Challenges, and Practical Considerations**  
   Donisch, Leo, Sigurd Schacht, Carsten Lanquillon.

3. **FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness**  
   Tri Dao, Daniel Y. Fu, Stefano Ermon, Atri Rudra, Christopher Ré.
