# Collaborative-Perception

This repository collects recent advances in **collaborative / cooperative / multi-agent perception** for **V2I / V2V / V2X** autonomous driving. 
Generally, the works are classified into the following types:
- Communication Reduction
- Model/Pipeline Optimization
- Robustness
- Security
- Heterogeneity
- Dataset
- Others

## Communication Reduction

Reducing the communication burden to save bandwidth resources and mitigate the perception delay is one of the most significant subtopics of collaborative perception.
Recently, many papers have focused on optimizing communication loads of collaborative perception, which are listed in chronological order.

- **What2comm** (What2comm: Towards Communication-Efficient Collaborative Perception via Feature Decoupling) [[paper](https://dl.acm.org/doi/abs/10.1145/3581783.3611699)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2XSet, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2023
  - Feature: A novel decoupling-based communication mechanism to promote comprehensive and pragmatic information transmission among heterogeneous agents.

- **Where2comm** (Where2comm: Efficient Collaborative Perception via Spatial Confidence Maps) [[paper&review](https://openreview.net/forum?id=dLL4KXzKUpS)] [[code](https://github.com/MediaBrain-SJTU/where2comm)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, DAIR-V2X, V2X-Sim, CoPerception-UAV
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2022
  - Feature: A novel _communication-efficient_ multi-agent collaborative perception framework with the guidance of **spatial confidence maps**.

- **CRCNet** (Complementarity-Enhanced and Redundancy-Minimized Collaboration Network for Multi-agent Perception) [[paper](https://dl.acm.org/doi/abs/10.1145/3503161.3548197)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2022
  - Feature: Highlight two criteria for selecting features to _save communication bandwidth_ including **complementarity maximization** and **redundancy minimization**.

- **DiscoNet** (Learning Distilled Collaboration Graph for Multi-Agent Perception) [[paper&review](https://openreview.net/forum?id=ZRcjSOmYraB)] [[code](https://github.com/ai4ce/DiscoNet)]
  - Mode: Early Collaboration (teacher model), Intermediate Collaboration (student model)
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2021
  - Feature: A teacher-student framework to train DiscoGraph via **knowledge distillation**; A matrix-valued edge weight in DiscoGraph.

- **MASH** (Overcoming Obstructions via Bandwidth-Limited Multi-Agent Spatial Handshaking) [[paper](https://arxiv.org/abs/2107.00771)] [[code](https://github.com/yifanlu0227/CoAlign)]
  - Mode: Late Collaboration
  - Dataset: AirSim
  - Task: Segmentation
  - Input: RGB Image
  - Publication: IROS 2021
  - Feature: Extending the 1D handshaking mechanism of When2com to a **2D spatial handshaking mechanism**.

- **When2com** (When2com: Multi-Agent Perception via Communication Graph Grouping) [[paper](https://arxiv.org/abs/2006.00176)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-MAP
  - Task: Segmentation, Classification
  - Input: RGB Image
  - Publication: CVPR 2020
  - Feature: A unified framework that learns both how to construct **communication groups** and _when to communicate_; A collaborative multi-agent semantic segmentation dataset, **AirSim-MAP**.

- **Who2com** (Who2com: Collaborative Perception via Learnable Handshake Communication) [[paper](https://arxiv.org/abs/2003.09575)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-CP (has an asynchronous issue between views)
  - Task: Segmentation
  - Input: RGB Image
  - Publication: ICRA 2020
  - Feature: A **multi-stage handshake communication mechanism** where the neural network can learn to compress relevant information needed for each stage; Using a matching score to determine _who to connect with_.

    

## Model/Pipeline Optimization

Currently, several works have focused on improving collaborative perception performance by leveraging advanced models or refining existing pipelines. Here are some examples.

- **AdaFusion** (Adaptive Feature Fusion for Cooperative Perception Using LiDAR Point Clouds) [[paper](https://arxiv.org/abs/2208.00116)] [[code](https://github.com/DonghaoQiao/Adaptive-Feature-Fusion-for-Cooperative-Perception)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, CODD
  - Task: Detection
  - Input: Point Cloud
  - Publication: WACV 2023
  - Feature: Adaptive feature fusion models with trainable feature selection modules to enhance perception accuracy.

- **Coopernaut** (COOPERNAUT: End-to-End Driving with Cooperative Perception for Networked Vehicles) [[paper](https://arxiv.org/abs/2205.02222)] [[code](https://github.com/UT-Austin-RPL/Coopernaut)]
  - Mode: Intermediate Collaboration
  - Dataset: AutoCastSim (simulator)
  - Task: Planning
  - Input: Point Cloud
  - Publication: CVPR 2022
  - Feature: An **end-to-end driving model** with cooperative perception via V2V channels; A network-augmented autonomous driving simulation framework **AUTOCASTSIM**.

- **MP-Pose** (Multi-Robot Collaborative Perception with Graph Neural Networks) [[paper](https://arxiv.org/abs/2201.01760)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-MAP
  - Task: Segmentation
  - Input: RGB Image
  - Publication: ICRA 2022
  - Feature:  The first work employing **GNN** to solve a multi-view/multi-robot perception task with real robot image data.

## Robustness

Due to the common localization noise in the real world, the collaborative perception performance would degrade below single-agent performance. It is paramount to study the robustness against pose noise in vehicle-to-everything communication systems and to design models that can explicitly reason under such noise. Here are the relevant papers listed in chronological order.

- **FeaCo** (FeaCo: Reaching Robust Feature-Level Consensus in Noisy Pose Conditions) [[paper](https://dl.acm.org/doi/abs/10.1145/3581783.3611880)] [[code](https://github.com/jmgu0212/FeaCo)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2V4Real
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2023
  - Feature: Robust Feature-level Consensus among collaborating agents in noisy pose conditions without additional training. 

- **CoAlign** (Robust Collaborative 3D Object Detection in Presence of Pose Errors) [[paper](https://arxiv.org/abs/2211.07214)] [[code](https://github.com/yifanlu0227/CoAlign)]
  - Mode: Intermediate Collaboration, Late Collaboration
  - Dataset: OPV2V, V2X-Sim, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICRA 2023
  - Feature: A novel agent-object pose graph modeling to enhance pose consistency among collaborating agents.

- **Double-M Quantification** (Uncertainty Quantification of Collaborative Detection for Self-Driving) [[paper](https://arxiv.org/abs/2209.08162)] [[code](https://github.com/coperception/double-m-quantification)]
  - Mode: Early Collaboration, Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICRA 2023
  - Feature: The proposed Double-M Quantification is the first attempt to estimate the uncertainty (both the epistemic uncertainty and aleatoric uncertainty)  of collaborative object detection.

- **SyncNet** (Latency-Aware Collaborative Perception) [[paper](https://arxiv.org/abs/2207.08560)] [[code](https://github.com/MediaBrain-SJTU/SyncNet)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: ECCV 2022
  - Feature: Formulate the _communication latency challenge_ in collaborative perception for the first time and propose a novel latency-aware collaborative perception system; A novel latency compensation module, termed _SyncNet_, to
achieve feature-level synchronization.

- **IA-RCP** (Robust Collaborative Perception against Communication Interruption) [[paper](https://learn-to-race.org/workshop-ai4ad-ijcai2022/papers.html)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: IJCAI 2022
  - Feature: The first work to address the _interruption issue_ in collaborative perception.

- **Robust V2V** (Learning to Communicate and Correct Pose Errors) [[paper](https://arxiv.org/abs/2011.05289)] [[code](https://github.com/yifanlu0227/CoAlign)]
  - Mode: Intermediate Collaboration
  - Dataset: V2V-Sim (not publicly available)
  - Task: Detection, Forecasting
  - Input: Point Cloud
  - Publication: CoRL 2020
  - Feature: A **pose regression** module predicts the relative _pose noise_ between a pair of vehicles; A **consistency module** based on Markov random field with Bayesian reweighting; An **attention module** to filter out remaining _noisy messages_ before aggregation. 

## Security

In collaborative perception systems, shared information can be modified to execute adversarial attacks on deep learning models that are widely employed in modern systems.
By studying adversarial robustness, we can enhance modern security protocols by introducing an additional layer of fault tolerance at the neural network level. Below are the papers regarding the security and privacy issues in collaborative perception systems.

- **Adversarial V2V** (Adversarial Attacks On Multi-Agent Communication) [[paper](https://arxiv.org/abs/2101.06560)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2V-Sim (not publicly available)
  - Task: Adversarial Attack
  - Input: Point Cloud
  - Publication: ICCV 2021
  - Feature: Investigate _adversarial attacks_ in multi-agent perception where **perturbations** are applied to learned intermediate representations.
 
## Heterogeneity

Multi-agents could have different types of sensors (Lidar/Camera) and communication links (V2V/V2X). Meanwhile, the downstream tasks could also be different for different agents, which could cause heterogeneity and hetero-modal. To facilitate large-scale deployment of collaborative perception, how to handle the heterogeneity in multi-agent perception systems is a major concern. Following are recent works focusing on heterogeneity in collaborative perception systems.

- **MAMP** (Model-Agnostic Multi-Agent Perception Framework) [[paper](https://arxiv.org/abs/2203.13168)] [[code](https://github.com/DerrickXuNu/model_anostic)]
  - Mode: Late Collaboration
  - Dataset: OPV2V
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICRA 2023
  - Feature:  A model-agnostic multi-agent perception framework to reduce the negative effect caused by the model discrepancies without sharing the model information.

- **MPDA** (Bridging the Domain Gap for Multi-Agent Perception) [[paper](https://arxiv.org/abs/2210.08451)] [[code](https://github.com/DerrickXuNu/MPDA)]
  - Mode: Intermediate Collaboration
  - Dataset: V2XSet
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICRA 2023
  - Feature: The first work to bridge the domain gap for multi-agent perception (Assume different agents have different neural networks).

- **V2X-ViT** (V2X-ViT: Vehicle-to-Everything Cooperative Perception with Vision Transformer) [[paper](https://arxiv.org/abs/2203.10638)] [[code](https://github.com/DerrickXuNu/v2x-vit)]
  - Mode: Intermediate Collaboration
  - Dataset: V2XSet
  - Task: Detection
  - Input: Point Cloud
  - Publication: ECCV 2022
  - Feature:  The first unified transformer architecture for V2X perception, which can capture the _heterogeneity_ nature of V2X systems with strong robustness against various noises.

- **STAR** (Multi-Robot Scene Completion: Towards Task-Agnostic Collaborative Perception) [[paper&review](https://openreview.net/forum?id=hW0tcXOJas2)] [[code](https://github.com/coperception/star)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Segmentation, Detection
  - Input: Point Cloud
  - Publication: CoRL 2022
  - Feature: The first _task-agnostic_ collaborative perception paradigm that learns a single collaboration module in a self-supervised manner for different downstream tasks.

## Dataset

Several simulated/real-world and V2V/V2X collaborative perception datasets have been created recently.

- **TCLF** (DAIR-V2X: A Large-Scale Dataset for Vehicle-Infrastructure Cooperative 3D Object Detection) [[paper](https://arxiv.org/abs/2204.05575)] [[code](https://github.com/AIR-THU/DAIR-V2X)]
  - Mode: Late Collaboration
  - Dataset: **DAIR-V2X**
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: CVPR 2022
  - Type: Real-world, V2X

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

Below are other interesting directions in collaborative perception.

- **DUSA** (DUSA: Decoupled Unsupervised Sim2Real Adaptation for Vehicle-to-Everything Collaborative Perception) [[paper](https://arxiv.org/abs/2310.08117)] [[code](https://github.com/refkxh/DUSA)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2XSet, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2023
  - Feature:  New unsupervised sim2real domain adaptation method for V2X collaborative detection.
