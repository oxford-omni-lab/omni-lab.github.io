---
title: "OMNI Lab - Research"
layout: textlay
excerpt: "OMNI Lab -- Research"
sitemap: false
permalink: /research/
---

# Research Highlights

---

![]({{ site.url }}{{ site.baseurl }}/images/respic/atlas_image.png){: style="width: 300px; float: left;margin-right: 30px; border: 10px"}

## Machine learning to characterise fetal brain maturation
<div style="text-align: justify">
Normal development of the human brain can be characterized by precisely timed growth and folding of its surface (cortex), with deviations often associated with poor cognitive outcomes. Advances in ultrasound (US) imaging technology now make it possible to visualize the cortex and screen for brain abnormalities before birth, from as early as 14 gestational weeks (GW). However, diagnostic confirmation currently relies on expensive, specialised magnetic resonance (MR) imaging, only after a referral from an initial US scan. Referral procedures delay diagnosis until 20 GW (at the earliest), and limit detailed evaluation to a minority of fetuses (<1%). US imaging is a first step in the pregnancy care continuum, and unlike MRI, available worldwide. As such, dedicated US-based tools would transform the detection of anomalies and injuries from specialist care to standard, routine procedure. Furthermore, such tools have the potential to make high-quality brain assessment accessible to more babies and earlier in pregnancy.

Working closely with the INTERGROWTH-21st Consortium and healthcare professionals, we develop a range of computational tools for assessing fetal health from US images. Our findings demonstrate that US images contain more neurostructural detail than is currently used in the clinic. Our early work confirmed the link between brain maturation and sonographic patterns observable across gestation ([Namburete et al, 2015](https://www.sciencedirect.com/science/article/pii/S136184151400190X)), demonstraing that an machine learning (ML) approach can outperform current clinical methods for age estimation in the 2nd and 3rd trimesters of pregnancy: a period of large biological variations in the fetal cohort, and the timeframe within which the 'anomaly scan' is offered to expectant mothers. This work was extended upon by using deep learning (DL) to estimate fetal age based on indivudal cortical folds ([Wyburd et al, 2021](https://link.springer.com/chapter/10.1007/978-3-030-87735-4_23)). This is a significant advance considering that pregnancy dating is a cornerstone of obstetrics, yet methodological improvements have stagnated since the introduction of US scanning to fetal growth monitoring in the 1970s.

We continue to apply ML and DL ideas to address problems unique to medical image data. For example, we have developed a series of segmention methods to delineate the brain ([Moser et al, 2022](https://www.sciencedirect.com/science/article/pii/S1053811922004608)), the cortex ([Wyburd et al, 2020](https://link.springer.com/chapter/10.1007/978-3-030-52791-4_5)), and subcortical cortical structures ([Hesse et al, 2022](https://www.sciencedirect.com/science/article/pii/S1053811922002452)). To highlight one such tool, we developed a unified network that delineates the fetal skull, detects the location of brain structures, and predicts a transformation for co-alignment of brain images to a common coordinate system. This network constitutes a key step in the construction of the first US-based atlas (digital map) of the fetal brain, which serves as a population reference against which to compare individual subjects for automated detection of developmental anomalies which has become of the background of ([Namburete et al, 2023]()).

</div>
---- 


![]({{ site.url }}{{ site.baseurl }}/images/respic/scn2aMut.png){: style="width: 300px; float: left;margin-right: 30px; border: 10px"}

## Scalable deep learning for large medical datasets
<div style="text-align: justify">

  
In order to deploy our DL algorithms to study new cohorts, we need to address the fact that data collected at different clinical sites may contain unique signatures introduced by the particular equipment used and the local population distribution (e.g. sex, medical history). Multi-site medical data tends to contain hidden biases that are not visible to a human observer, but result in a drop in the predictive power of DL models. Furthermore, the increasing digitisation in the medical domain has led to the creation of a large amount of data, which will continue to rise in the near future. As these datasets become increasingly available, there is an opportunity to combine data from multiple sites to generate unified “big data” stores. This has the advantage of improving the anatomical diversity of training datasets, thereby providing a better overall understanding of disease mechanisms, and increasing statistical power. However, it also leads to an undesirable increase in non-biological variance, even when attempts are made to reduce these by following standardised acquisition protocols or using identical medical equipment. We discussed the challenges of big Data and clinical machine learning in a recent review article ([Dinsdale et al, 2022](https://www.sciencedirect.com/science/article/pii/S0896627322008170)).
  
  
Our recent work is exploring how adversarial learning can be adapted to the task of harmonisation or confound removal ([Dinsdale et al, 2023](https://www.sciencedirect.com/science/article/pii/S1053811920311745)). Our domain adaptation approach aims to produce feature representations that are invariant to a pre-selected confounding variable (e.g. sex, scanner, test site) by optimizing custom loss functions (e.g. gradient reversal following an iterative training schedule) that actively discourage our models from learning the inherent biases within the datasets. Our results show successful application of this technique in regression and tissue segmentation tasks: the most common challenges in the medical domain. 

</div>

![]({{ site.url }}{{ site.baseurl }}/images/respic/asdcnv.png){: style="width: 300px; float: left;margin-right: 30px; border: 10px"}

## Improving neural networks to improve memory efficiency and reduce dataset bias 
<div style="text-align: justify">
  
With the increasing popularity of deep learning, we have began to developed work that tackles the major bottlenecks in the field of medical image analysis, namely: (1) shortage of expertly labelled data for model training; (2) the large memory footprint required by convolutional neural networks, which limits their deployability on portable devices; and (3) the fact that models optimally adapt to the distribution represented by the training dataset, at the risk of becoming biased and not generalising to new datasets. 
  
 To address the shortage of data labels, we have developed omni- and self-supervised learning algorithms that exploit a small annotated dataset (e.g. 5% of total size)  ([Huang et al, 2018](https://link.springer.com/chapter/10.1007/978-3-030-00928-1_65)),([Venturini et al, 2020](https://link.springer.com/chapter/10.1007/978-3-030-59710-8_67)). These algorithms increase model performance by refining their parameters during an iterative increase in dataset size. We have demonstrated that this method accurately generates new data annotations without human input on a large dataset of unseen 3D brain images. Compared to manual annotation of the full dataset, this reduced workload by 90%, from over 360 hours to 36 hours.
  
To address the second challenge, we have developed a method to compress large convolutional neural networks such that they require less memory and are able to run in real-time on mobile devices. Our approach uses separable convolutions and knowledge distillation to reduce the memory footprint of the UNet (a widely used network for medical image segmentation), for example, by 420x from 118 MB to 280 KB, with a 13-fold speed-up, yet with negligible compromise in performance  ([Vaze et al, 2020](https://ieeexplore.ieee.org/abstract/document/8999615)). Experiments on modern tablets and smartphones showed real-time processing of US images, with potential applications in point-of-care US.
  
Our approach to overcoming the third challenge is to explicitly impose an ‘unbiasing’ term on the network during the training procedure. Specifically, by using gradient reversal techniques, we encourage the network to learn features that are agnostic to confounding variables (e.g. scanner type, sex, etc), such that the overall model is invariable to these when processing new (and often smaller) datasets, thus becoming more generalizable ([Dinsdale et al, 2023](https://www.sciencedirect.com/science/article/pii/S1053811920311745)).
</div>
---
  
![]({{ site.url }}{{ site.baseurl }}/images/respic/asdcnv.png){: style="width: 300px; float: left;margin-right: 30px; border: 10px"}

## Towards translation into clinical workflow
<div style="text-align: justify">

### Model compression
  
 Much of the unprecedented success of deep learning models can be attributed to the construction of increasingly large convolutional neural networks (CNNs), containing several parameters that can capture the complexity of growing datasets and diverse tasks. The trend has been that the larger the network, the better the performance. However, large CNNs are computationally demanding as they require more expensive and specialised GPU hardware, take longer to run, and require vast memory stores. These limitations make them difficult to redistribute, and thus impractical for many real-world applications. One such scenario is in transferring our validated algorithms to operate on standard medical workstations or to mobile devices that interface with portable, point-of-care ultrasound probes.
  
One way to address this is to compress the models in such a way that model size (parameter count) is reduced, while minimising the loss in accuracy. To date, my group has explored model compression using separable convolution kernels (to reduce filter sizes) and knowledge distillation: a “teacher-student” network setup in which only the task-relevant weights learned by the larger teacher network are transferred to a much smaller student network ([Vaze et al, 2020](https://ieeexplore.ieee.org/abstract/document/8999615)). This preliminary work led to a reduction in network size, with negligible compromise in accuracy for processing ultrasound images on Android-based mobile devices.
  
Our recent work has shown that model pruning is an appropiate comppression stratgey for a range of medical imaging tasks ([Dinsdale et al, 2022](https://www.sciencedirect.com/science/article/pii/S1361841522002213)). Pruning involves reducing any redundancy in a large, trained network, either by weight or channel pruning. Our proposed method reduced the size of a network by 85% (in terms of parameters) whilst achieving a higher performance.
  
  
### Broadening access to 3D brain scanning
In neuroimaging research, 3D image data is the mainstay for representing anatomical details. However, in conventional clinical practice, pre- and post-natal assessments are performed with 2D video or static US images. The sonographers need to interpret the relationships between the 2D views and 3D brain anatomy and mentally reconstruct a 3D image given just the 2D information. This process requires in-depth understanding of fetal anatomy and experience in ultrasound imaging, both of which require adequately skilled personnel, which may be scarce in resource-constrained settings.
  
Towards applying our structural atlas to routine care, our ongoing work is exploring the localization of 2D video frames in their anatomically corresponding 3D (atlas) space ([Yeung et al, 2021](https://www.sciencedirect.com/science/article/pii/S136184152100044X)). We are treating this as a self-supervised learning problem. Inspired by relation networks and neural radiance fields (neRF), we are designing a pairwise comparison module to evaluate the geometrical relationships between different planes. While fusing feature representations from different image frames during prediction, attention mechanisms are applied to dynamically assign importance to the information from all other input video frames. The goal is to reconstruct a 3D brain scan from 2D freehand video acquisitions. We foresee that this would have applications in perinatal clinics, and in LMICs ([Yeung et al, 2021](https://arxiv.org/pdf/2109.12108.pdf)).
</div>
---

