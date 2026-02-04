---
layout: default
title: Adversarial Driving Scene Generation Challenge @ TopoCoT Workshop 2026
description: Challenge SOTA E2E AD models by curating adversarial driving scenes
---

:wave: Welcome to the **Adversarial Driving Scene Generation Challenge** organized at :wave:
[<img class="rounded-rect" src="assets/imgs/wacv2026.png" width="420px" alt="WACV 2026"/>](https://wacv2026.thecvf.com)
{: .text-center}

**Workshop / Challenge Info:**

<div class="container">
  <img class="rounded-rect" src="assets/imgs/AD0.jpg" alt="Challenge Overview Figure"/>
</div>
{: .text-center}


---
## 📄 **Paper** {#paper}

 **Reference Paper (arXiv)**: [Challenger: Affordable adversarial driving video generation](https://arxiv.org/abs/2505.15880)

---

## 📌 **Overview** {#overview}

**The Reality Gap:**
While autonomous driving systems have made remarkable progress, they remain fragile in "corner cases"—rare, unexpected, or aggressive scenarios that often lead to safety-critical failures. Ensuring robustness in these conditions is currently a major bottleneck for real-world deployment. 

**The Challenge:**
Current benchmarks lack the ability to systematically stress-test End-to-End (E2E) driving models against these edge cases. This competition addresses that gap by focusing on Adversarial Driving Scene Generation. Your task is to create synthetic driving scenes that feature adversarial or aggressive traffic participants. 

**The Objective:**
This challenge flips the traditional evaluation paradigm. Instead of optimizing for higher driving scores, we incentivize you to generate scenarios that degrade model performance. Success is measured by your ability to induce failures in state-of-the-art E2E driving models while maintaining plausibility, helping the community to better understand and fix critical model weaknesses. 

---

## 🎯 **Task** {#task}

Your mission is to generate **adversarial driving scenarios** that induce failures in SOTA E2E autonomous driving models. You will achieve this by subtly modifying real-world scenes to create difficult but physically plausible "corner cases". 

**The Process:**
* **Input Data**: You will use abstract driving scenes originated from the **nuScenes** dataset.
* **Trajectory Manipulation**: You are allowed to manipulate the trajectory of **exactly one** background vehicle (the "adversarial agent"). 
* **Objective**: Create an aggressive or unexpected interaction with the autonomous ego vehicle. 

**Strict Constraints:**
* **Minimum Safety Distance**: The adversarial vehicle must never approach within [TBD] meters (no ramming). 
* **No Background Collisions**: Must not collide with other background traffic. 
* **Drivable Area**: Must remain within road boundaries at all times. 
---

## ⚙️ **Evaluation** {#evaluation}

Submissions are evaluated through a three-stage pipeline to ensure realism and effectiveness: 

1. **Kinematic Rectification**: Ensures the trajectory is smooth and physically executable via LQR controller. This step enforces dynamic feasibility, ensuring the adversarial vehicle's movement is physically executable.
2. **Neural Rendering**: Converts scenarios into high-fidelity RGB video clips for realistic visual testing.
3. **Performance Testing & Scoring**: Clips are fed into four SOTA E2E AD models in an **open-loop setting**. 

* **Primary Metric:** The models are evaluated based on their **Average Collision Rate** across your generated scenes. 
* **Ranking:** Contrary to standard benchmarks, **higher is better**. A higher rate indicates a more successful adversarial scenario.

---

## 🏆 **Baseline & Benchmark** {#baseline}

<div class="container">
  <img class="rounded-rect" src="assets/imgs/AD1.png" alt="Adversarial scenarios and performance degradation"/>
</div>
{: .text-center}
*Photorealistic adversarial driving scenarios and observed performance degradation in terms of collision rate.* 

---

## 📚 **Recommended Readings & Citations** {#citations}

Participants are encouraged to read and cite the following work: 

```bibtex
@article{xu2025challenger,
  title={Challenger: Affordable adversarial driving video generation},
  author={Xu, Zhiyuan and Li, Bohan and Gao, Huan-ang and Gao, Mingju and Chen, Yong and Liu, Ming and Yan, Chenxu and Zhao, Hang and Feng, Shuo and Zhao, Hao},
  journal={arXiv preprint arXiv:2505.15880},
  year={2025}
}

<style>
  footer, .site-footer, .owner {
    display: none !important;
  }
</style>
