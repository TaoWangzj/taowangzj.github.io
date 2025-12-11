---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>


Currently, I am a researcher and engineer in the Image Quality and Perception Algorithms Center of vivo, working on low-level vision and multimodal generation. Before that, I received the Ph.D. degree from the School of Computer Science, Nanjing University (NJU), 2025, under the supervision of Prof. [Tong lu](https://cs.nju.edu.cn/lutong/). From September 2024 to March 2025, I worked as an academic intern at VIVO (Shanghai). I have published over 40+ peer-reviewed papers in top-tier journals and conferences, like IJCV, TIP, ICCV, ECCV, NeurIPS, SIGGRAPH, AAAI, IJCAI, ACM MM, etc. I am a reviewer for TPAMI, TIP, CVPR, ICCV, ECCV, NeurIPS, SIGGRAPH, ICLR, AAAI, IJCAI, etc.



We are hiring self-motivated research interns. If you are interested in our group, please feel free to contact me by E-mail: [taowangzj@gmail.com](mailto:taowangzj@gmail.com).

<span class="anchor" id="research"></span>
# Research
I am interested in several topics in computer vision and machine learning. Specifically, my research focuses on creative AI, such as image/video enhancement and synthesis, AI generated content (AIGC).


# 🔥 News
- *2025.12*: 🎉 LLFormer V2 has been released, the <a href="https://github.com/TaoWangzj/LLFormerV2">link</a>.
- *2025.11*: 🎉 Our Deep IR survey repository is available, the <a href="https://github.com/TaoWangzj/Awesome-Image-Restoration">link</a>.
- *2025.09*: 🎉 Joining vivo.
- *2025.07*: 🎉 Updating new homepage.
- *2025.06*: 🎉 Two papers were accepted by ICCV 2025 (MOERL and MaterialMVP).
- *2025.05*:    Successfully defended PhD dissertation.
- *2025.04*: 🎉 One paper was accepted by SIGGRAPH 2025 (video super-resolution).
- *2025.03*: 🎉 One paper was accepted by PR (low-light enhancement).
- *2024.12*: 🎉 Two papers were accepted by ICASSP 2025 (face enhancement, UDC image restoration).
- *2024.11*: 🎉 BYD scholarship of Nanjing University.
- *2024.08*: 🎉 One paper was accepted by TCSVT (face Anti-spoofing).
- *2024/07*: 🎉 One paper was accepted by ACM MM 2024 (video face restoration). 
- *2024/07*: 🎉 One paper was accepted by ECAI 2024 (correspondence pruning). 
- *2024/07*: 🎉 One paper was accepted by ECCV 2024 (personalized text-to-image generation).
- *2024/03*: 🎉 One paper was accepted by TCSVT (blind face restoration). 
- *2024/03*: 🎉 One paper was accepted by IJCV (adverse weather restoration). 
- *2023/12*: 🎉 One paper was accepted by AAAI 2024 (correspondence pruning). 
- *2023/11*: 🎉 One paper was accepted by TCSVT (under-display camera face image restoration).  
- *2023/11*: Sun-Xiangzhen scholarship of Nanjing University.
- *2023/09*: 🎉 One paper was accepted by NeurIPS 2023 (punctuation-level attack for text models).
- *2023/09*: 🎉 One paper was accepted by TCSVT (a comprehensive benchmark for image deblurring).
- *2023/09*: 🎉 One paper was accepted by PR (image dehazing).
- *2023/04*: 🎉 One paper was accepted by IJCAI 2023 (graph representation learning).
- *2023/04*: 🎉 One paper was accepted by TCSVT (rgb-d salient object detection).
- *2023/01*: 🎉 One paper was selected for an ORAL presentation at AAAI 2023 (UHD low-light enhancement). 
- *2022/11*: 🎉 One paper was accepted by AAAI 2023 (UHD low-light enhancement). 
- *2022/11*: One paper was online in Arxiv (face restoration survey), see the <a href="https://www.51cto.com/article/740298.html">news</a>.


<span class="anchor" id="projects"></span>
# Projects 

<div class='paper-box'><div class='paper-box-image'><div><div class="badge"> </div><img src='images/MOERL.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[MOERL: When Mixture-of-Experts Meet Reinforcement Learning for Adverse Weather Image Restoration]()

**T. Wang**, P. Xia, B. Li, P. Jiang, Z. Kong, K. Zhang, T. Lu, W. Luo

Proc. of International Conference on Computer Vision (ICCV), 2025.

[**PDF**]() [**Code**]()
- A general backbone with RL for image restoration in adverse weather conditions.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge"> </div><img src='images/GridFormer2.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[GridFormer: Residual Dense Transformer with Grid Structure for Image Restoration in Adverse Weather Conditions](https://arxiv.org/abs/2305.17863)

**T. Wang**, K. Zhang, Z. Shao, W. Luo, B. Stenger, T. Lu, TK. Kim, W. Liu, H. Li

International Journal of Computer Vision (IJCV), 2024.

[**PDF**](https://link.springer.com/article/10.1007/s11263-024-02056-0) [**Code**](https://github.com/TaoWangzj/GridFormer)
- A general Transformer backbone for image restoration in adverse weather conditions.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge"> </div><img src='images/LLFormer2.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Ultra-High-Definition Low-Light Image Enhancement: A Benchmark and Transformer-Based Method](https://arxiv.org/pdf/2212.11548.pdf)

**T. Wang**, K. Zhang, T. Shen, W. Luo, B. Stenger, T. Lu

Proc. of the Association for the Advancement of Artificial Intelligence (AAAI), 2023.

[**PDF**](https://arxiv.org/pdf/2212.11548.pdf) [**Code**](https://github.com/TaoWangzj/LLFormer) 
- The first work proposing the UHD-LLIE problem and addressing it with Transformer.
</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge"> </div><img src='images/LLDiffusion.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[LLDiffusion: Learning Degradation Representations in Diffusion Models for Low-Light Image Enhancement](https://www.sciencedirect.com/science/article/abs/pii/S0031320325002882)

**T. Wang**, K. Zhang, Y. Zhang, W. Luo, B. Stenger, T. Lu, TK. Kim, W. Liu

Pattern Recognition (PR), 2025.

[**PDF**](https://www.sciencedirect.com/science/article/abs/pii/S0031320325002882) [**Code**](https://github.com/TaoWangzj/LLDiffusion) 
- Image enhancement with diffusion model and degradation learning.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge"> </div><img src='images/HCD.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Restoring Vision in Hazy Weather with Hierarchical Contrastive Learning](https://www.sciencedirect.com/science/article/pii/S0031320323006544)

**T. Wang**, G. Tao, W. Lu, K. Zhang, W. Luo, X. Zhang, T. Lu

Pattern Recognition (PR), 2023.

[**PDF**](https://www.sciencedirect.com/science/article/pii/S0031320323006544) 
- A framework using contrastive learning to produce visually pleasing images.
</div>
</div>


<span class="anchor" id="services"></span>
# Professional Activities

Conference Reviewer: CVPR, ECCV, ICCV, NeurIPS, ICLR, SIGGRAPH, AAAI, IJCAI, ACM MM, etc.

Journal Reviewer: TPAMI, TIP, PR, TCSVT, CVIU, TII, TMM, ITS, NN, etc.


<span class='anchor' id='Visitor'></span>
# ⭐️ Visitor ![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=taowangzj.github.io)

<script type="text/javascript" id="clustrmaps" src="//clustrmaps.com/map_v2.js?d=HpDM8e07AdKUqxj7S-j1Bl0FyDqsg4moaSLvltwybqo&cl=ffffff&w=a"></script>

