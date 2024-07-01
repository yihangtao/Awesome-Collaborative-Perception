# Collaborative-Perception

This repository collects recent advances in **collaborative / cooperative / multi-agent perception** for **V2I / V2V / V2X** autonomous driving. 
Generally, the works are classified into the following types:
- Communication Reduction
- Model Enhancement
- Robustness
- Security
- Others

## Communication Reduction

Reducing the communication burden to save bandwidth resources and mitigate the perception delay is one of the most significant subtopics of collaborative perception.
Recently, many papers have focused on optimizing communication loads of collaborative perception, which are listed in chronological order.

- **Who2com** (Who2com: Collaborative Perception via Learnable Handshake Communication) [[paper](https://arxiv.org/abs/2003.09575)] [[code](https://github.com/GT-RIPL/MultiAgentPerception)]
  - Mode: Intermediate Collaboration
  - Dataset: AirSim-CP (has an asynchronous issue between views)
  - Task: Segmentation
  - Input: RGB Image
  - Publication: ICRA 2020
  - Feature: A multi-stage handshake communication mechanism where the neural network can learn to compress relevant information needed for each stage; Using matching score to determine _who to connect with_.
    

## Model Enhancement

## Robustness

## Security

## Others
