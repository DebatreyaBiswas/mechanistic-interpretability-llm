# mechanistic-interpretability-llm
Experiments in changing LLM behavior using steering vectors and activation engineering
# GPT-2 Semantic Asymmetry & Activation Steering

This repository contains the experimental code, `Steering_vectorization_LLM`[cite: 1], for investigating how Large Language Models (specifically GPT-2 Small) encode safety features and sentiments within their activation space[cite: 2]. 

Standard alignment methods, such as RLHF, treat model behaviors as surface-level constraints[cite: 2]. This project takes a mechanistic interpretability approach, utilizing forward hooks to inject steering vectors directly into Layer 6 of the GPT-2 residual stream during inference[cite: 2]. 

The primary goal of this codebase is to test the hypothesis of feature superposition: **Are semantic features in LLMs perfectly symmetrical?**[cite: 2]

---

## Key Experimental Findings

By extracting steering vectors using contrastive prompt pairs (e.g., love vs. hate, insults vs. compliments), the experiments in this notebook reveal that model representations are actually highly asymmetric[cite: 2]:

* **The Inverse Steering Failure:** Subtracting a positive sentiment vector does not make the model hostile; instead, it resists the polarity shift and breaks down into repetition loops[cite: 2]. 
* **Contextual Aggression:** Direct injection of an aggression vector forces the model to output hostility, but the model actively attempts to fabricate a narrative context (like a corporate firing) to rationalize its sudden aggression[cite: 2].
* **The "Yes Man" Effect:** The model is highly susceptible to sycophancy (e.g., agreeing that 2+2=5) but heavily resists reality denial (e.g., refusing to deny the Earth is round)[cite: 2]. 
* **Semantic Collapse:** The boundary of a model's activation space is not static[cite: 2]. Pushing steering vectors too hard causes semantic collapse, but the threshold depends heavily on the internal "friction" between the prompt and the injected vector[cite: 2].

---

## Usage & Experiments

This notebook contains self-contained code to replicate several experiments[cite: 2]:
1. Sentiment Vector Extraction & Injection[cite: 2]
2. Inverse Steering[cite: 2]
3. Aggression Vector Extraction & Injection[cite: 2]
4. Reality Denial & Sycophancy Testing[cite: 2]
5. Safety Stress Testing (Inducing Semantic Collapse)[cite: 2]

> **Disclaimer:** *The aggressive outputs generated in this notebook are the result of controlled interpretability experiments designed to study AI safety mechanisms and geometric structures of semantic features*[cite: 2]. *This research does not promote harmful language*[cite: 2].

---

## Citation & Preprint

The underlying theory, mathematical framework, and detailed analysis of these activation steering experiments are covered in my submitted book chapter manuscript[cite: 2]:

> **Investigating Semantic Asymmetry in LLM Safety Circuits: A Comparative Analysis of Inverse Steering and Feature Injection in GPT-2** (Under Review / Submitted for Publication)[cite: 2]
> *Debatreya Biswas*, Nova Science Publishers, 2026[cite: 2].

If you utilize this codebase, the extracted steering vectors, or the experimental insights in your academic work, please don't forget to cite my work.
