# human-explanation-evaluation
## Overview
This is the official repository for the paper [```Are Human Explanations Always Helpful?  Towards Objective Evaluation of Human Natural Language Explanations```](https://arxiv.org/abs/2305.03117) accepted at ACL2023 for oral presentation.

We provide an objective evaluation to quantify human-annotated explanations’ helpfulness toward model performance. In addition, we examine explanation utilities during fine-tuning and inference. 

Our evaluation consists of the following novelties:
1. A prompt-based unified data format for various tasks
2. A novel metric **TREU** evaluates explanations’ helpfulness at different stages
3. An evaluation with 5 datasets and 2 models justifies the faithfulness and consistency of TREU compared with the Simulatability score

## Todo

- [ ] We plan to provide some simple code to support fine-tuning / inference with our unified structure


## Contributions

### Utility of Explanations at Fine-tuning and inference

<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/f61fc211-69a4-436d-8383-14bb559510a7" alt="In-depth Experiment on CoS-E v1.0" title="In-depth Experiment on CoS-E v1.0" width=400/>
</p>
<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/153fbfc0-80a7-44cc-a445-8bc3fc6d27b2" alt="In-depth Experiment on ECQA" title="In-depth Experiment on ECQA" width=400/>
</p>

Figure 1. In-depth experiment on CoS-E v1.0 (top) and ECQA (bottom) with different amounts of training data. We repeat the process 3 times to obtain an average score.

Observations from the diagrams above by comparing different settings: 

![image](https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/e5a445d3-5240-4c41-9a7b-cb1ba54b71f7)

### Unified Data Format

Convert NLP tasks into a unified multiple-choice task to minimize the influence of task differences with 2 settings:
* **Baseline**: no explanation 
* **Infusion**: leverage explanation as additional input

<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/6dffebf7-2b8e-40a8-a878-8e56a1ab7c4a" alt="Unified Data Format" title="Unified Data Format" width=500/>
</p>

Figure 2. Unified structure of Baseline and Infusion settings. Black bold texts are fixed prompts. The color schema follows: blue denotes question content; green denotes choices; orange denotes explanations. We provide examples of **Infusion** in e-SNLI (classification) as well as CoS-E and ComVE (multi-choice). 


### **TREU** Metric

<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/c2fb0226-3221-44d4-8d42-1893a3e6e3b8" alt="TREU Metric" title="TREU Metric" />
</p>


Figure 3. Formula of our **TREU** metric. It evaluates helpfulness of explanations at fine-tuning and inference stages. Model subscript/superscript denotes 𝐹𝑖𝑛𝑒𝑡𝑢𝑛𝑒 𝑆𝑒𝑡𝑡𝑖𝑛𝑔 / 𝐼𝑛𝑓𝑒𝑟𝑒𝑛𝑐𝑒 𝑆𝑒𝑡𝑡𝑖𝑛𝑔. The existing Simulatability Score only evaluates inference stage (second part of **TREU**). 

### Human-annotated Explanations Evaluation


<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/5e807f14-8026-4831-910c-710144338532" alt="Datasets" title="Datasets" width=600/>
</p>

We perform the evaluation on 5 Datasets with human-annotated explanations and 2 model architectures, using our **TREU** metric and the established Simulatability score

<p align="middle">
  <img src="https://github.com/WorkInTheDark/human-explanation-evaluation/assets/68862265/c80f3a06-344a-4afc-a488-1beb30ef23d5" alt="Datasets" title="Datasets" width=600/>
</p>



## Citation
Our Paper is accepted to ACL 2023, you may cite:
```
@article{yao2023human,
  title={Are human explanations always helpful? towards objective evaluation of human natural language explanations},
  author={Yao, Bingsheng and Sen, Prithviraj and Popa, Lucian and Hendler, James and Wang, Dakuo},
  journal={arXiv preprint arXiv:2305.03117},
  year={2023}
}
```
