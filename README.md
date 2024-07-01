# Collaborative-Perception

This repository collects recent advances in **collaborative / cooperative / multi-agent perception** for **V2I / V2V / V2X** autonomous driving. 
Generally, the works are classified into the following types:
- Communication Reduction
- Model Enhancement
- Robustness
- Security
- Dataset
- Others

## Communication Reduction

Reducing the communication burden to save bandwidth resources and mitigate the perception delay is one of the most significant subtopics of collaborative perception.
Recently, many papers have focused on optimizing communication loads of collaborative perception, which are listed in chronological order.

- **DiscoNet** (Learning Distilled Collaboration Graph for Multi-Agent Perception) [[paper&review](https://openreview.net/forum?id=ZRcjSOmYraB)] [[code](https://github.com/ai4ce/DiscoNet)]
  - Mode: Early Collaboration (teacher model), Intermediate Collaboration (student model)
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2021
  - Feature: A teacher-student framework to train DiscoGraph via knowledge distillation; A matrix-valued edge weight in DiscoGraph.

- **MASH** (Overcoming Obstructions via Bandwidth-Limited Multi-Agent Spatial Handshaking) [[paper](https://arxiv.org/abs/2107.00771)] [[code](https://github.com/yifanlu0227/CoAlign)]
  - Mode: Late Collaboration
  - Dataset: AirSim
  - Task: Segmentation
  - Input: RGB Image
  - Publication: IROS 2021
  - Feature: Extending the 1D handshaking mechanism of When2com to a 2D spatial handshaking mechanism.

- **When2com** (When2com: Multi-Agent Perception via Communication Graph Grouping) [[paper](https://arxiv.org/abs/2006.00176)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-MAP
  - Task: Segmentation, Classification
  - Input: RGB Image
  - Publication: CVPR 2020
  - Feature: A unified framework that learns both how to construct communication groups and when to communicate; A collaborative multi-agent semantic segmentation dataset, AirSim-MAP.

- **Who2com** (Who2com: Collaborative Perception via Learnable Handshake Communication) [[paper](https://arxiv.org/abs/2003.09575)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-CP (has an asynchronous issue between views)
  - Task: Segmentation
  - Input: RGB Image
  - Publication: ICRA 2020
  - Feature: A multi-stage handshake communication mechanism where the neural network can learn to compress relevant information needed for each stage; Using a matching score to determine _who to connect with_.

    

## Model Enhancement

Currently, several works have focused on improving collaborative perception performance by leveraging advanced models or refining the existing model structures. Here are some examples.

- **MP-Pose** (Multi-Robot Collaborative Perception with Graph Neural Networks) [[paper](https://arxiv.org/abs/2201.01760)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-MAP
  - Task: Segmentation
  - Input: RGB Image
  - Publication: ICRA 2022
  - Feature:  The first work employing GNN to solve a multi-view/multi-robot perception task with real robot image data.

## Robustness

Due to the common localization noise in the real world, the collaborative perception performance would degrade below single-agent performance. It is paramount to study the robustness against pose noise in vehicle-to-everything communication systems and to design models that can explicitly reason under such noise. Here are the relevant papers listed in chronological order.

- **Robust V2V** (Learning to Communicate and Correct Pose Errors) [[paper](https://arxiv.org/abs/2011.05289)] [[code](https://github.com/yifanlu0227/CoAlign)]
  - Mode: Intermediate Collaboration
  - Dataset: V2V-Sim (not publicly available)
  - Task: Detection, Forecasting
  - Input: Point Cloud
  - Publication: CoRL 2020
  - Feature: A _pose regression_ module predicts the relative pose noise between a pair of vehicles; A _consistency module_ based on Markov random field with Bayesian reweighting; An _attention module_ to filter out remaining noisy messages before aggregation. 

## Security

In collaborative perception systems, shared information can be modified to execute adversarial attacks on deep learning models that are widely employed in modern systems.
By studying adversarial robustness, we can enhance modern security protocols by introducing an additional layer of fault tolerance at the neural network level. Below are the papers regarding the security and privacy issues in collaborative perception systems.

- **Adversarial V2V** (Adversarial Attacks On Multi-Agent Communication) [[paper](https://arxiv.org/abs/2101.06560)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2V-Sim (not publicly available)
  - Task: Adversarial Attack
  - Input: Point Cloud
  - Publication: ICCV 2021
  - Feature: Investigate adversarial attacks in multi-agent perception where perturbations are applied to learned intermediate representations.

## Dataset

Several simulated/real-world and V2V/V2X collaborative perception datasets have been created recently.

- **AttFuse** (OPV2V: An Open Benchmark Dataset and Fusion Pipeline for Perception with Vehicle-to-Vehicle Communication) [[paper](https://arxiv.org/abs/2109.07644)] [[code](https://github.com/DerrickXuNu/OpenCOOD)]
  - Mode: Intermediate Collaboration
  - Dataset: **OPV2V**
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICRA 2022
  - Type: Simulated, V2V

- **When2com** (When2com: Multi-Agent Perception via Communication Graph Grouping) [[paper](https://arxiv.org/abs/2006.00176)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: **AirSim-MAP**
  - Task: Segmentation, Classification
  - Input: RGB Image
  - Publication: CVPR 2020
  - Type: Simulated, Drones



## Others
