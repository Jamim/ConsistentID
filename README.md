<p align="center">
  <img src="https://github.com/JackAILab/ConsistentID/assets/135965025/c0594480-d73d-4268-95ca-5494ca2a61e4" height=100>

</p>

<!-- ## <div align="center"><b>ConsistentID</b></div> -->

<div align="center">
  
## ConsistentID : Portrait Generation with Multimodal Fine-Grained Identity Preserving  [![Paper page](https://huggingface.co/datasets/huggingface/badges/resolve/main/paper-page-md-dark.svg)]()
[📄[Paper](https://arxiv.org/abs/2404.16771)] &emsp; [🚩[Project Page](https://ssugarwh.github.io/consistentid.github.io/)] &emsp; [🖼[Gradio Demo](http://consistentid.natapp1.cc/)] <br>

[🤗[Faster Demo](https://huggingface.co/spaces/JackAILab/ConsistentID)] &emsp; <br>

</div>

### 🌠  **Key Features:**

1. Portrait generation with extremely high **ID fidelity**, without sacrificing diversity, text controllability.
2. Introducing **FaceParsing** and **FaceID** information into the Diffusion model.
3. Rapid customization **within seconds**, with no additional LoRA training.
4. Can serve as an **Adapter** to collaborate with other Base Models alongside LoRA modules in community.

---
## 🔥 **Examples**

<p align="center">
  
  <img src="https://github.com/JackAILab/ConsistentID/assets/135965025/f949a03d-bed2-4839-a995-7b451d8c981b" height=450>


</p>


## 🚩 To-Do List
Your star will help facilitate the process.
- [x] Release training, evaluation code, and demo!
- [ ] Retrain with more data and the SDXL base model to enhance aesthetics and generalization.
- [ ] Release a multi-ID input version to guide the improvement of ID diversity.
- [ ] Optimize training and inference structures to further improve text following and ID decoupling capabilities.

## 🏷️ Abstract

This is a work in the field of AIGC that introduces FaceParsing information and FaceID information into the Diffusion model. Previous work mainly focused on overall ID preservation, even though fine-grained ID preservation models such as InstantID have recently been proposed, the injection of facial ID features will be fixed. In order to achieve more flexible consistency maintenance of fine-grained IDs for facial features, a batch of 50000 multimodal fine-grained ID datasets was reconstructed for training the proposed FacialEncoder model, which can support common functions such as personalized photos, gender/age changes, and identity confusion.

At the same time, we have defined a unified measurement benchmark FGIS for Fine-Grained Identity Preservice, covering several common facial personalized character scenes and characters, and constructed a fine-grained ID preservation model baseline.

Finally, a large number of experiments were conducted in this article, and ConsistentID achieved the effect of SOTA in facial personalization task processing. It was verified that ConsistentID can improve ID consistency and even modify facial features by selecting finer-grained prompts, which opens up a direction for future research on Fine-Grained facial personalization.


## 🔧 Requirements

- Python >= 3.8 (Recommend to use [Anaconda](https://www.anaconda.com/download/#linux) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html))
- [PyTorch >= 2.0.0](https://pytorch.org/)
- cuda==11.8

```bash
conda create --name ConsistentID python=3.8.10
conda activate ConsistentID
pip install -U pip

# Install requirements
pip install -r requirements.txt
```

## 📦️ Data Preparation

Prepare Data in the following format

    ├── data
    |   ├── JSON_all.json 
    |   ├── resize_IMG # Imgaes 
    |   ├── all_faceID  # FaceID
    |   └── parsing_mask_IMG # Parsing Mask 

The .json file should be like
```
[
    {
        "resize_IMG": "Path to resized image...",
        "parsing_color_IMG": "...",
        "parsing_mask_IMG": "...",
        "vqa_llva": "...",
        "id_embed_file_resize": "...",
        "vqa_llva_more_face_detail": "..."
    },
    ...
]
```

## 🚀 Train
Ensure that the workspace is the root directory of the project.

```setup
bash train_bash.sh
```

## 🧪 Infer
Ensure that the workspace is the root directory of the project.

```setup
python infer.py
```

## ⏬ Model weights
We are hosting the model weights on **huggingface** to achieve a faster and more stable demo experience, so stay tuned ~

The pre-trained model parameters of the model can now be downloaded on [Google Drive](https://drive.google.com/file/d/1jCHICryESmNkzGi8J_FlY3PjJz9gqoSI/view?usp=drive_link) or [Baidu Netdisk](https://pan.baidu.com/s/1NAVmH8S7Ls5rZc-snDk1Ng?pwd=nsh6).


## Acknowledgement
* Inspired from many excellent demos and repos, including [IPAdapter](https://github.com/tencent-ailab/IP-Adapter), [FastComposer](https://github.com/mit-han-lab/fastcomposer), [PhotoMaker](https://github.com/TencentARC/PhotoMaker). Thanks for their great works!
* Thanks to the open source contributions of the following work: [face-parsing.PyTorch](https://github.com/zllrunning/face-parsing.PyTorch), [LLaVA](https://github.com/haotian-liu/LLaVA), [insightface](https://github.com/deepinsight/insightface), [FFHQ](https://github.com/NVlabs/ffhq-dataset), [CelebA](https://github.com/switchablenorms/CelebAMask-HQ), [SFHQ](https://github.com/SelfishGene/SFHQ-dataset).
* 🤗 Thanks to the huggingface gradio team [ZeroGPUs](https://github.com/huggingface) for their free GPU support!

## Disclaimer
This project strives to impact the domain of AI-driven image generation positively. Users are granted the freedom to create images using this tool, but they are expected to comply with local laws and utilize it responsibly. The developers do not assume any responsibility for potential misuse by users.

## Citation
If you found this code helpful, please consider citing:
~~~
@article{huang2024consistentid,
  title={ConsistentID: Portrait Generation with Multimodal Fine-Grained Identity Preserving},
  author={Huang, Jiehui and Dong, Xiao and Song, Wenhui and Li, Hanhui and Zhou, Jun and Cheng, Yuhao and Liao, Shutao and Chen, Long and Yan, Yiqiang and Liao, Shengcai and others},
  journal={arXiv preprint arXiv:2404.16771},
  year={2024}
}
~~~


