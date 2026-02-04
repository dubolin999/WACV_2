---
layout: default
title: Robust and Safe Embodied Intelligence in Challenging Scenarios @ TopoCoT Workshop 2026
description: The unified Generalist VLA Agent capable of performing perception, reasoning, and planning tasks simultaneously within unstructured driving contexts.
---

👋 Welcome to the **Robust and Safe Embodied Intelligence in Challenging Scenarios** organized at 👋
[<img class="rounded-rect" src="wacv2026.png" width="420px" alt="WACV 2026"/>](https://wacv2026.thecvf.com)
{: .text-center}

**Workshop / Challenge Info:**

<div class="container">
  <img class="rounded-rect" src="RS0.jpg" alt="Challenge Overview Figure"/>
</div>
{: .text-center}

---

## 📄 **Paper** {#paper}

**Reference Paper (arXiv)**: [Impromptu VLA: Open Weights and Open Data for Driving Vision-Language-Action Models](https://arxiv.org/abs/2505.23757)

---

## 📌 **Overview** {#overview}

**The Reality Gap:**
Autonomous driving systems have achieved remarkable proficiency in structured environments such as urban centers and highways. However, the "last mile" of truly ubiquitous autonomy lies in the ability to navigate **unstructured scenarios**—the chaotic, unpredictable, and "corner case" environments where current models frequently falter.

**The Challenge:**
To bridge this gap, this challenge leverages the **Impromptu VLA Dataset**, a large-scale collection of roughly 80,000 clips curated specifically to capture diverse and challenging unstructured scenarios. Participants are invited to develop **Vision-Language-Action (VLA)** models that can not only perceive and reason about complex environments but also generate safe and accurate planning trajectories.

<div class="container">
  <img class="rounded-rect" src="RS1.jpg" alt="Challenge Overview Figure"/>
</div>
{: .text-center}

---

## 🎯 **Task** {#task}

The challenge is structured around a **Planning-Oriented Question-Answering (Q&A)** format. Models must process multi-view images to generate text-based reasoning and vector-based trajectory outputs.

**1. Scene Understanding & Perception (Q&A):**
* **Vulnerable Road User (VRU) Identification**: Detect pedestrians, cyclists, or motorcyclists in challenging lighting or occlusion.
* **Traffic Signal Detection**: Identify the status of traffic lights (Red, Green, Yellow, None) even when they are non-standard.

**2. Reasoning & Prediction (Q&A):**
* **Dynamic Object Prediction**: Predict the motion intention (Speed and Path) of unconventional obstacles.
* **Meta-Action Planning**: Generate high-level decisions (e.g., "Decelerate and Nudge Left") based on the unstructured context.
* **Drivable Area**: The ego-vehicle must remain within road boundaries at all times.

**3. End-to-End Trajectory Planning:**
* Given the ego-vehicle’s past state (1.5s history), predict future waypoints for the next 5 seconds.

---

## ⚙️ **Evaluation** {#evaluation}

Evaluation is conducted on the Impromptu VLA Validation Set. Performance is assessed using two primary categories of metrics:

**1. Perception & Reasoning Metrics (Accuracy)**
For text-generation tasks, we calculate exact match accuracy against the ground truth (Higher is better).
* **V.R.U. Accuracy**: Identifying vulnerable road users.
* **T. Light Accuracy**: Classification of traffic signal states.
* **Dyn. Obj. Accuracy**: Precision of motion intention predictions.
* **Meta-Planning (M.P.) Accuracy**: Correctness of high-level driving decisions.

**2. Action Metric (Trajectory L2 Error)**
For the end-to-end planning task, we measure the Euclidean distance between predicted waypoints and ground truth (Lower is better).
* **L2 Error (meters)**: Calculated at 1s, 2s, 3s, and 4s horizons.
* **Average L2**: The final ranking will heavily weight the Average L2 Error across all time steps.

---

## 📚 **Recommended Readings & Citations** {#citations}

Participants are encouraged to read and cite the following work:

```bibtex
@article{chi2025impromptu,
  title={Impromptu VLA: Open Weights and Open Data for Driving Vision-Language-Action Models},
  author={Chi, Haohan and Gao, Huan-ang and Liu, Ziming and Liu, Jianing and Liu, Chenyu and Li, Jinwei and Yang, Kaisen and Yu, Yangcheng and Wang, Zeda and Li, Wenyi and others},
  journal={arXiv preprint arXiv:2505.23757},
  year={2025}
}
