# Collaborative-Perception

This repository collects recent advances in **collaborative / cooperative / multi-agent perception** for **V2I / V2V / V2X** autonomous driving. 
Generally, the works are classified into the following types:
- Communication Reduction
- Model Enhancement
- Robustness
- Security
- Heterogeneity
- Dataset
- Others

## Communication Reduction

Reducing the communication burden to save bandwidth resources and mitigate the perception delay is one of the most significant subtopics of collaborative perception.
Recently, many papers have focused on optimizing communication loads of collaborative perception, which are listed in chronological order.

- **CRCNet** (Complementarity-Enhanced and Redundancy-Minimized Collaboration Network for Multi-agent Perception) [[paper](https://dl.acm.org/doi/abs/10.1145/3503161.3548197)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2022
  - Feature: Highlight two criteria for selecting features to save communication bandwidth including complementarity maximization and redundancy minimization.

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

- **SyncNet** (Latency-Aware Collaborative Perception) [[paper](https://arxiv.org/abs/2207.08560)] [[code](https://github.com/MediaBrain-SJTU/SyncNet)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: ECCV 2022
  - Feature: Formulate the communication latency challenge in collaborative perception for the first time and propose a novel latency-aware collaborative perception system; A novel latency compensation module, termed _SyncNet_, to
achieve feature-level synchronization.

- **IA-RCP** (Robust Collaborative Perception against Communication Interruption) [[paper](https://learn-to-race.org/workshop-ai4ad-ijcai2022/papers.html)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: IJCAI 2022
  - Feature: The first work to address the interruption issue in collaborative perception.

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
 
## Heterogeneity

Multi-agents could have different types of sensors (Lidar/Camera) and communication links (V2V/V2X). Meanwhile, the downstream tasks could also be different for different agents, which could cause heterogeneity and hetero-modal. To facilitate large-scale deployment of collaborative perception, how to handle the heterogeneity in multi-agent perception systems is a major concern. Following are recent works focusing on heterogeneity in collaborative perception systems.

- **V2X-ViT** (V2X-ViT: Vehicle-to-Everything Cooperative Perception with Vision Transformer) [[paper](https://arxiv.org/abs/2203.10638)] [[code](https://github.com/DerrickXuNu/v2x-vit)]
  - Mode: Intermediate Collaboration
  - Dataset: V2XSet
  - Task: Detection
  - Input: Point Cloud
  - Publication: ECCV 2022
  - Feature:  The first unified transformer architecture for V2X perception, which can capture the heterogeneity nature of V2X systems with strong robustness against various noises.

- **STAR** (Multi-Robot Scene Completion: Towards Task-Agnostic Collaborative Perception) [[paper&review](https://openreview.net/forum?id=hW0tcXOJas2)] [[code](https://github.com/coperception/star)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Segmentation, Detection
  - Input: Point Cloud
  - Publication: CoRL 2022
  - Feature: The first task-agnostic collaborative perception paradigm that learns a single collaboration module in a self-supervised manner for different downstream tasks.

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
