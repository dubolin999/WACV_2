---
layout: default
title: Robust and Safe Embodied Intelligence in Challenging Scenarios @ TopoCoT Workshop 2026
description: The unified Generalist VLA Agent capable of performing perception, reasoning, and planning tasks simultaneously within unstructured driving contexts.
---

:wave: Welcome to the **Robust and Safe Embodied Intelligence in Challenging Scenarios** organized at :wave:
[<img class="rounded-rect" src="/wacv2026.png" width="420px" alt="WACV 2026"/>](https://wacv2026.thecvf.com)
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

Autonomous driving systems have achieved remarkable proficiency in structured environments such as urban centers and highways, where lane markings are clear and traffic flows are predictable. However, the "last mile" of truly ubiquitous autonomy lies in the ability to navigate unstructured scenarios—the chaotic, unpredictable, and "corner case" environments where current models frequently falter.
These unstructured settings encompass rural tracks with unclear boundaries, temporary construction zones with non-standard traffic rules, unconventional dynamic obstacles (such as animals or erratic actors), and adverse road conditions like extreme weather or debris. Existing datasets predominantly capture structured traffic, leaving a critical blind spot in the training and evaluation of robust AI drivers.
To bridge this gap, this challenge leverages the Impromptu VLA Dataset, a large-scale collection of roughly 80,000 clips curated specifically to capture these diverse and challenging unstructured scenarios. Participants are invited to develop Vision-Language-Action (VLA) models that can not only perceive and reason about these complex environments but also generate safe and accurate planning trajectories.

---

## 🎯 **Task** {#task}

The challenge is structured around a **Planning-Oriented Question-Answering (Q&A)** format. Participants will be provided with multi-view images and corresponding prompts. The model must process this visual information to generate text-based reasoning and vector-based trajectory outputs.

**1.	Scene Understanding & Perception (Q&A):**
* **Vulnerable Road User (VRU) Identification**: Detect the presence of pedestrians, cyclists, or motorcyclists in challenging lighting or occlusion.
* **Traffic Signal Detection**: Correctly identify the status of traffic lights (Red, Green, Yellow, None) even when they are temporary or non-standard. 

**2.	Reasoning & Prediction (Q&A):**
* **Dynamic Object Prediction**: Predict the motion intention (Speed and Path) of unconventional obstacles in the scene. 
* **Meta-Action Planning**: Generate high-level decisions for the ego-vehicle (e.g., "Decelerate and Nudge Left") based on the unstructured context. 
* **Drivable Area**: Must remain within road boundaries at all times.

**3.	End-to-End Trajectory Planning:**
* Given the ego-vehicle’s past state (1.5s history), predict the future waypoints for the next 5 seconds. 
---

## ⚙️ **Evaluation** {#evaluation}

Evaluation will be conducted on the Impromptu VLA Validation Set. Following the methodology established in the paper (Table 4), performance will be assessed using two primary categories of metrics: Q&A Accuracy for perception/reasoning tasks and L2 Error for trajectory generation.

1. **Perception & Reasoning Metrics (Accuracy)**
   For the text-generation tasks, we calculate the exact match accuracy for the generated tokens against the ground truth. Higher is better.
* **V.R.U. Accuracy:** Measures the ability to correctly identify vulnerable road users. 
* **T. Light Accuracy:** Measures the correct classification of traffic signal states.
* **Dyn. Obj. Accuracy:** Measures the precision of motion intention predictions for other agents. 
* **Meta-Planning (M.P.) Accuracy:** Measures the correctness of the high-level driving decision. 
2. **Action Metric (Trajectory L2 Error)**
  For the end-to-end planning task, we measure the Euclidean distance between the predicted waypoints and the ground truth trajectory. Lower is better.
* **L2 Error (meters):** Calculated at specific time horizons: 1s, 2s, 3s, and 4s. 
* **Average L2:** The final ranking will heavily weight the Average L2 Error across all time steps, as this indicates the model's ability to maintain a safe path over a longer horizon in unpredictable scenarios.

Participants must balance the multi-task nature of the challenge; as shown in our baseline experiments, models that effectively leverage the synergy between reasoning (Q&A) and action (Trajectory) achieve the lowest error rates.

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

<style>
  footer, .site-footer, .owner {
    display: none !important;
  }
</style>
