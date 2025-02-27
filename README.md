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

- **CodeFilling** (Communication-Efficient Collaborative Perception via Information Filling with Codebook) [[paper](https://arxiv.org/abs/2405.04966)] [[code](https://github.com/PhyllisH/CodeFilling)]
  - Mode: Intermediate Collaboration
  - Dataset: DAIR-V2X, OPV2VH+
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: CVPR 2024
  - Feature: The proposed codebook-based message representation enables the transmission of integer codes, rather than high-dimensional feature maps; The proposed information-filling-driven message selection optimizes local messages to
collectively fill each agent’s information demand, preventing information overflow among multiple agents.

- **CMiMC** (What Makes Good Collaborative Views? Contrastive Mutual Information Maximization for Multi-Agent Perception) [[paper](https://arxiv.org/abs/2403.10068)] [[code](https://github.com/77SWF/CMiMC)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: AAAI 2024
  - Feature: Preserve discriminative information of individual views in the collaborative view by maximizing mutual information between pre- and post-collaboration features while enhancing the efficacy of collaborative views by minimizing the loss function of downstream tasks.

- **FFNet** (Flow-Based Feature Fusion for Vehicle-Infrastructure Cooperative 3D Object Detection) [[paper&review](https://openreview.net/forum?id=gsglrhvQxX)] [[code](https://github.com/haibao-yu/FFNet-VIC3D)]
  - Mode: Intermediate Collaboration
  - Dataset: DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2023
  - Feature: A flow-based feature fusion framework for VIC3D object detection. FFNet transmits feature flow to generate aligned features for data fusion.

- **How2comm** (How2comm: Communication-Efficient and Collaboration-Pragmatic Multi-Agent Perception) [[paper&review](https://openreview.net/forum?id=Dbaxm9ujq6)] [[code](https://github.com/ydk122024/How2comm)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2XSet, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2023
  - Feature: A mutual information-aware communication mechanism to maximally sustain the informative features shared by collaborators; A flow-guided delay compensation strategy to predict future characteristics
from collaborators and eliminate feature misalignment due to temporal asynchrony; A pragmatic collaboration transformer is introduced to integrate holistic spatial semantics and temporal context clues among agents.

- **TransIFF** (TransIFF: An Instance-Level Feature Fusion Framework for Vehicle-Infrastructure Cooperative 3D Detection with Transformers) [[paper](https://openaccess.thecvf.com/content/ICCV2023/html/Chen_TransIFF_An_Instance-Level_Feature_Fusion_Framework_for_Vehicle-Infrastructure_Cooperative_3D_ICCV_2023_paper.html)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICCV 2023
  - Feature: An instance-level feature fusion framework with transformers that can effectively reduce bandwidth usage; Align the domain gaps between vehicle and infrastructure features, and improve the robustness of feature fusion, leading to a high cooperative perception accuracy.

- **UMC** (UMC: A Unified Bandwidth-Efficient and Multi-Resolution Based Collaborative Perception Framework) [[paper](https://arxiv.org/abs/2303.12400)] [[code](https://github.com/ispc-lab/UMC)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICCV 2023
  - Feature: A novel trainable multi-resolution and selective-region (MRSR) mechanism, achieving higher quality and lower bandwidth for collaborative communication.

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

- **MRCNet** Multi-Agent Collaborative Perception via Motion-Aware Robust Communication Network [[paper](https://openaccess.thecvf.com/content/CVPR2024/html/Hong_Multi-agent_Collaborative_Perception_via_Motion-aware_Robust_Communication_Network_CVPR_2024_paper.html)] [[code](https://github.com/IndigoChildren/collaborative-perception-MRCNet)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2XSet, V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: CVPR 2024
  - Feature: MRCNet consists of two main components: multi-scale robust fusion (MRF) addresses pose noise by developing cross-semantic multi-scale enhanced aggregation to fuse features of different scales, while motion enhanced mechanism (MEM) captures motion context to compensate for information blurring caused by moving objects.

- **CoBEVFlow** (Robust Asynchronous Collaborative 3D Detection via Bird's Eye View Flow) [[paper&review](https://openreview.net/forum?id=UHIDdtxmVS)] [[code](https://github.com/MediaBrain-SJTU/CoBEVFlow)]
  - Mode: Intermediate Collaboration
  - Dataset: DAIR-V2X, IRV2V
  - Task: Detection
  - Input: Point Cloud
  - Publication: NeurIPS 2023
  - Feature: Compensate motions to align asynchronous collaboration messages sent by multiple agents.

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

- **ROBOSAC** (Among Us: Adversarially Robust Collaborative Perception by Consensus) [[paper](https://arxiv.org/abs/2303.09495)] [[code](https://github.com/coperception/ROBOSAC)]
  - Mode: Intermediate Collaboration
  - Dataset: V2X-Sim
  - Task: Detection
  - Input: Point Cloud
  - Publication: ICCV 2023
  - Feature: Develop ROBOSAC, a scalable, generalizable, and generally-applicable adversarially robust collaborative perception framework via multi-robot consensus.

- **Adversarial V2V** (Adversarial Attacks On Multi-Agent Communication) [[paper](https://arxiv.org/abs/2101.06560)] [~~code~~]
  - Mode: Intermediate Collaboration
  - Dataset: V2V-Sim (not publicly available)
  - Task: Adversarial Attack
  - Input: Point Cloud
  - Publication: ICCV 2021
  - Feature: Investigate _adversarial attacks_ in multi-agent perception where **perturbations** are applied to learned intermediate representations.
 
## Heterogeneity

Multi-agents could have different types of sensors (Lidar/Camera) and communication links (V2V/V2X). Meanwhile, the downstream tasks could also be different for different agents, which could cause heterogeneity and hetero-modal. To facilitate large-scale deployment of collaborative perception, how to handle the heterogeneity in multi-agent perception systems is a major concern. Following are recent works focusing on heterogeneity in collaborative perception systems.

- **HEAL** (An Extensible Framework for Open Heterogeneous Collaborative Perception) [[paper&review](https://openreview.net/forum?id=KkrDUGIASk)] [[code](https://github.com/yifanlu0227/HEAL)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V-H, DAIR-V2X
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: ICLR 2024
  - Feature: Establishes a unified feature space with initial agents via a novel multi-scale foreground-aware Pyramid Fusion network, which accommodates continually emerging new heterogeneous agent types into collaborative perception, while ensuring high perception performance and low integration cost.

- **DI-V2X** (DI-V2X: Learning Domain-Invariant Representation for Vehicle-Infrastructure Collaborative 3D Object Detection) [[paper](https://arxiv.org/abs/2312.15742)] [[code](https://github.com/Serenos/DI-V2X)]
  - Mode: Intermediate Collaboration
  - Dataset: V2XSet, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: AAAI 2024
  - Feature: Bridge the data-level domain gap caused by sensor differences in the context of V2X collaborative perception, which is achieved by incorporating a domain-invariant distillation framework.

- **HM-ViT** (HM-ViT: Hetero-Modal Vehicle-to-Vehicle Cooperative Perception with Vision Transformer) [[paper](https://arxiv.org/abs/2304.10628)] [[code](https://github.com/XHwind/HM-ViT)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: ICCV 2023
  - Feature: A novel transformer framework (HM-ViT) for multi-agent hetero-modal cooperative perception, capable of capturing the modality-specific characteristics and heterogeneous 3D interactions.

- **BM2CP** {BM2CP: Efficient Collaborative Perception with LiDAR-Camera Modalities} [[paper&review](https://openreview.net/forum?id=uJqxFjF1xWp)] [[code](https://github.com/byzhaoAI/BM2CP)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, DAIR-V2X
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: CoRL 2023
  - Feature: A novel framework for multi-modal collaborative perception, where modal fusion is guided by LiDAR and collaborative fusion is guided by modality.

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

- **CoopDet3D** (TUMTraf V2X Cooperative Perception Dataset) [[paper](https://arxiv.org/abs/2403.01316)] [[code](https://github.com/tum-traffic-dataset/coopdet3d)]
  - Mode: Intermediate Collaboration
  - Dataset: **TUMTraf-V2X**
  - Task: Detection
  - Input: RGB Image, Point Cloud
  - Publication: CVPR 2024
  - Type: Real-world, V2X, Traffic violations 

- **V2XFormer** (DeepAccident: A Motion and Accident Prediction Benchmark for V2X Autonomous Driving) [[paper](https://arxiv.org/abs/2304.01168)] [[code](https://github.com/tianqi-wang1996/DeepAccident)]
  - Mode: Intermediate Collaboration
  - Dataset: **DeepAccident**
  - Task: Detection, Forecasting
  - Input: RGB Image
  - Type: Simulated, V2X, Accident scenarios

- **FF-Tracking** (V2X-Seq: The Large-Scale Sequential Dataset for the Vehicle-Infrastructure Cooperative Perception and Forecasting) [[paper](https://arxiv.org/abs/2305.05938)] [[code](https://github.com/AIR-THU/DAIR-V2X-Seq)]
  - Mode: Intermediate Collaboration
  - Dataset: **DAIR-V2X-Seq**
  - Task: Tracking
  - Input: Point Cloud
  - Publication: CVPR 2023
  - Type: Real-world, V2X, Large-scale trajectory

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

- **MACP** (MACP: Efficient Model Adaptation for Cooperative Perception) [[paper](https://arxiv.org/abs/2310.16870)] [[code](https://github.com/PurdueDigitalTwin/MACP)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2V4Real
  - Task: Detection
  - Input: Point Cloud
  - Publication: WACV 2024
  - Feature: A novel framework to empower adapting single-agent perception models to the cooperative perception, which is simple to implement and cost-effective to train.

- **DUSA** (DUSA: Decoupled Unsupervised Sim2Real Adaptation for Vehicle-to-Everything Collaborative Perception) [[paper](https://arxiv.org/abs/2310.08117)] [[code](https://github.com/refkxh/DUSA)]
  - Mode: Intermediate Collaboration
  - Dataset: OPV2V, V2XSet, DAIR-V2X
  - Task: Detection
  - Input: Point Cloud
  - Publication: MM 2023
  - Feature:  New unsupervised sim2real domain adaptation method for V2X collaborative detection.
