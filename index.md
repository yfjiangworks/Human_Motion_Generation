![Image](resources/fig1.png)


# Abstract

Recently, skeleton-based human action has become a hot research topic because the compact representation of human skeletons brings new blood to this research domain. As a result, researchers began to notice the importance of using RGB or other sensors to analyze human action by extracting skeleton information. Leveraging the rapid development of deep learning (DL), a significant number of skeleton-based human action approaches have been presented with fine-designed DL structures recently. However, a well-trained DL model always demands high-quality and sufficient data, which is hard to obtain without costing high expenses and human labor. In this paper, we introduce a novel data augmentation method for skeleton-based action recognition tasks, which can effectively generate high-quality and diverse sequential actions. In order to obtain natural and realistic action sequences, we propose a denoising diffusion probabilistic models (DDPMs) that can generate a series of synthetic action sequences, and its generation process is precisely guided by a spatial-temporal transformer (ST-Trans). Experimental results show that our method outperforms the state-of-the-art (SOTA) motion generation approaches on different naturality and diversity metrics. It proves that its high-quality synthetic data can also be effectively deployed to existing action recognition models with significant performance improvement. 

# Overview

![Image](resources/fig2.png)
<p align="center">
Overview of the proposed method. Orange arrows show the transformer-guided process, black arrows indicate the reverse denoising process, and the green arrow shows the translation process from the skeleton image representation to the 3D joint coordinate representation. Moreover, we denote spatial-temporal transformer as ST-Trans in short.
</p>

This paper proposes a novel action synthesis algorithm designed to improve skeleton-based action recognition performance in a data-scarcity situation. Specially, we introduce a conditionally generative model that (1) can generate natural action sequence with enough spatial-temporal information, rather than awkward or repeated ones, (2) is able to be conditioned by specific action categories so that the generation process is controllable, (3) is not constrained to a specific action domain, for instance, actions with sitting or standing poses, (4) does not rely on noisy training data, in other words, can be trained more efficiently and stably.

To achieve the above goals, we design a transformer-guided diffusion model, which consists of two main modules: a visual transformer (ViT) module and a denoising diffusion probabilistic models (DDPM) module. Specifically, the pretrained DDPM module cooperates with the pretrained ViT module through a guiding strategy so that DDPM is able to sample action sequences under the guidance of ViT. Therefore, it can generate a series of augmented action sequences with only an action label provided. In the above figure, with the help of the synthetic data, the action recognition model can maintain an acceptable performance when real training data is scarce.

# Synthetic acion sequences
![Image](resources/fig3.png)
<p align="center">
Examples of synthetic 'point to something' (top) and 'kick something' (bottom) action sequences.
</p>

# This work is under preprinting.
