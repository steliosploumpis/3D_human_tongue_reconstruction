# [3D human tongue reconstruction with adversarial surface generation](https://arxiv.org/abs/1911.08008)

 [Stylianos Ploumpis](https://www.imperial.ac.uk/people/s.ploumpis)<sup> 1,2 * </sup>, [Stylianos Moschoglou](https://www.doc.ic.ac.uk/~sm3515/)<sup> 1,2 * </sup>, Vasileios Triantafyllou <sup> 2</sup>, & [Stefanos Zafeiriou](https://wp.doc.ic.ac.uk/szafeiri/)<sup> 1,2</sup>
 <br/>
 <sup>1 </sup>Imperial College London, UK
 <br/>
 <sup>2 </sup> Huawei Techologies co. ltd
 <br> 
 <sup>* </sup> Indicates equal contribution




<br/>

<p align="center"><img width="100%" src="figures/teaser_fig_new.png" /></p>

<br/>

<p align="center"><img width="60%" src="figures/com_animate.gif" alt="Logo"></p>



## Abstract

3D face reconstruction from a single image is a task that has garnered increased interest in the Computer Vision community, especially due to its broad use in a number of applications such as realistic 3D avatar creation, pose invariant face recognition and face hallucination. Since the introduction of the 3D Morphable Model in the late 90’s, we witnessed an explosion of research aiming at particularly tackling this task. Nevertheless, despite the increasing level of detail in the 3D face reconstructions from single images mainly attributed to deep learning advances, finer and highly deformable components of the face such as the tongue are still absent from all 3D face models in the literature, although being very important for the realness of the 3D avatar representations. In this work we present the first, to the best of our knowledge, method that: a) accurately reconstructs the tongue by utilizing a novel GAN framework which directly models the surface distribution of the tongue from raw data without any preprocessing, and b) seamlessly merges it with the existing state-of-the-art face and head models. Moreover, we make publicly available to the community the first diverse tongue dataset, consisting of 5,200 raw scans of 1,500 individuals varying in gender, age, and ethnicity backgrounds. Finally, as we demonstrate in an extensive series of quantitative as well as qualitative experiments, our model proves to be robust and realistically captures the 3D tongue structure, even in adverse ``in-the-wild'' conditions. 

## Approach

<p align="center"><img width="100%" src="figures/method.png" /></p>
An illustration of our tongue reconstruction framework during inference. The embedding network predicts a latent 3D feature which is later transformed to the corresponding parametersptof the synthetic expression PCA via linear projection. The generator randomly predicts 10K points (z∼N(0, I)) that belong to the distribution of the tongue surface. This point-cloud is later utilized in the tongue optimization pipe-line which aims at refining the shape of the initialtongue expression.

<br/>

## TongueGAN
<p align="center"><img width="90%" src="figures/net_diagram_narrow.png" /></p>
TongueGAN architecture. Symbol $\mathbf{c}$ stands for row-wise concatenation along the channel dimension. Symbol $\circ$ stands for element-wise (\ie, Hadamard) product. The Generator inputs are: i) a Gaussian noise sample $\mathbf{z}$ and ii) a label $\mathbf{\tilde{y}}$ corresponding to a particular tongue, from which we want to sample a 3D point. The Discriminator input pairs are: i) $\left(\mathbf{y}, \mathbf{x}\right)$, where $\mathbf{y}$ is a label corresponding to a specific tongue and $\mathbf{x}$ a \textsl{real} 3D point belonging to the aforementioned tongue point-cloud (but sampled as explained in Section \ref{sec:novel_loss}), ii) $\left(\mathbf{\tilde{y}}, G\left(\mathbf{z},\mathbf{\tilde{y}}\right)\right)$, where $\mathbf{\tilde{y}}$ is a label corresponding to a tongue and $G\left(\mathbf{z}, \mathbf{\tilde{y}}\right)$ a generated point belonging to this tongue. The Discriminator is asked to distinguish the real from the fake (\ie, generated) pair.

<br/>

## Tongue Reconstruction Results from single images

<p align="center"><img width="100%" src="figures/qual_fig_new.png" /></p>

<br/>

## Citation
If you find this work is useful for your research, please cite our [paper](http://openaccess.thecvf.com/content_CVPR_2019/html/Ploumpis_Combining_3D_Morphable_Models_A_Large_Scale_Face-And-Head_Model_CVPR_2019_paper.html):

```


```

<br/>

## Public release Tongue dataset

<p align="center"><img width="60%" src="figures/raw_point_cloud_dataset_2.png" /></p>

