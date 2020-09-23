# Trojan Attack Overview
![Trojan attack](./images/STOP.svg)
<!--<img src="./images/STOP.png">-->
A Trojan attack demonstrating a backdoored model of a self-driving car run-ning a **STOP** sign that could cause a catastrophic accident. Left: Normal sign (benign input). Right: Trojaned sign (Tro-janed input with the Post-it note trigger) is recognized as a 100 km/h **speedlimit** by the Trojaned network.


# Overview of the Februus system
![overview](./images/overview.svg)
<!--<img src="./images/overview.svg">-->
Overview of the **Februus System**. The Trojaned input is processed through the **Trojan Removal** module that inspects and surgically removes the trigger. Subsequently, the damaged input is processed by the **Image Restoration** module to recover the damaged regions. The restored image is fed into the Trojaned DNN. ***TOP***: Without Februus, the Trojaned input will trigger the backdoor and be misclassified as a 100 km/h **SPEED LIMIT** sign. **BOTTOM**: With Februus deployed, the Trojaned DNN still correctly classifies the Trojaned input as a **STOP** sign



***The methods devised can successfully apply the notion of input sanitization realized in an unsupervised setting to the visual inputs of a deep neural network system. This is indeed a new finding.***

***Most interestingly, and perhaps for the first time, we show that deep perception models are able to achieve state-of-the-art performance post our proposed input sanitization method (that removes parts of an image and restores it prior to classification).***


Februus is an open source project that proposes, for the first time, the concept of sanitising inputs to deep neural network systems to provide a run time defence against Trojan attacks. The project is published as part of the following paper and if you re-use our work, please cite the following paper:

```
@inproceedings{doan2020februus,
title={Februus: Input Purification Defense Against Trojan Attacks on Deep Neural Network Systems},
author={Bao Gia Doan and Ehsan Abbasnejad and Damith C. Ranasinghe},
year = {2020},
booktitle = {Proceedings of the 36th Annual Computer Security Applications Conference (ACSAC)},
location = {Austin, TX, USA},
series = {ACSAC 2020}
}
```



## Contributions

1. We investigate a new defense concept---unsupervised *input sanitization for deep neural networks*---and propose a *system architecture* to realizing it. Our proposed architecture, ***Februus***, aims to *sanitize* inputs by: ***i)*** exploiting the Trojan introduced biases leaked in the network to localize and surgically remove triggers in inputs; and ***ii)*** *restoring* inputs for the classification task.

2. Our extensive evaluations demonstrate that our method is a robust defense against: ***i)*** input-agnostic Trojans---*our primary focus*; and ***ii)*** complex adaptive attacks (multiple advanced backdoor attack variants and attacks targeting Februus functions). For our study, we built *ten* Trojan networks with *five* different realistic and natural Trojan triggers of various complexity---such as a facial tattoo, flag lapel on a T-shirt.

3. Februus is efficacious. We show significant reductions in attack success rates, from 100% to near 0%, across all *four* datasets and multiple different input-agnostic triggers whilst retaining state-of-the-art performance on benign inputs and *all* sanitized inputs.

4. Februus is also highly effective against *multiple* complex adaptive attack variants---achieving reductions in attack success rates from 100% to near 0% for most cases.

5. Further, we demonstrate that Februss is an effective defense against triggers of increasing size covering up to 25% of the input image.

6. Significantly, we provide the first result for a defense against partial backdoor attacks: ***i)*** we implement and demonstrate resilience to the stealthy advanced Trojan attack---*Partial Backdoor Attack*---capable of evading state-of-the-art defense methods; and ***ii)*** we implement the adaptive attack, multiple triggers to multiple targets attack, shown to be able to fool other state-of-the-art defense methods and demonstrate the resilience of Februus to this evasive attack.

7. We contribute to the discourse in the discipline by releasing our Trojan model zoo---ten Trojan networks with five different naturalistic Trojan triggers. Code release and project artifacts are available from the Github repo.

*Github Link:* [![Github link](./images/GitHub-Mark-64px.png)](https://github.com/AdelaideAuto-IDLab/Februus)

Archived Version: [Februus](https://arxiv.org/abs/1908.03369)


