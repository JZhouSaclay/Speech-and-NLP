# Speech-and-NLP
Work of this class - Speech and NLP - at University Paris-Saclay

---

# Fantastically Ordered Prompts — Course Submission

**Course:** Speech and Language Processing
**Topic:** Prompt Order Sensitivity in Few-Shot In-Context Learning

This project reproduces and analyzes the paper
**“Fantastically Ordered Prompts and Where to Find Them”**,
with a focus on **entropy-based prompt order selection**, its **Chinese adaptation**, and its **behavior under limited model capacity**.

---

## 1. Reproduction

* We reproduce the **original pipeline** on **English SST-2 with GPT-2**.
* Results confirm the paper’s main findings:

  * strong prompt order sensitivity,
  * clear positive correlation between entropy and accuracy,
  * significant accuracy improvement when selecting top-$K$ prompts by entropy.

📁 **`English_version/`**

---

## 2. Extension (Chinese Setting)

* We adapt the method to **Chinese sentiment classification** using:

  * a Chinese GPT-2 medium model,
  * a balanced takeaway review dataset (4-shot, 24 prompt orders).
* Despite smaller model capacity, entropy-based selection still yields:

  * a **small but positive accuracy gain**,
  * a consistent entropy–accuracy trend.

📁 **`Chinese_version/`**

---

## 3. Analysis (Simplified Pipeline)

* We implement a **lightweight entropy pipeline** without synthetic probing.
* Controlled experiments show that:

  * entropy is weak as a per-example confidence signal,
  * fake (random) entropy does not correlate with accuracy,
  * entropy–accuracy correlation weakens in simplified or small-model settings.
* These analyses clarify **when and why** the method works.

📁 **`Chinese_version/` (analysis notebooks)**

---

## 4. Full Pipeline & Engineering Notes

* We also attempt a **full Chinese reproduction** of the authors’ codebase.
* This includes all debugging steps and intermediate failures.
* Scripts are intended to be executed **top-to-bottom**, even if some cells error.

📁 **`git_version/`**

---

## Takeaway

Entropy is an effective, label-free signal for selecting prompt orders in few-shot learning, but its effectiveness depends on **model scale** and **pipeline design**.
This project combines **faithful reproduction**, **cross-lingual extension**, and **controlled analysis** to expose both the strengths and limitations of the method.
