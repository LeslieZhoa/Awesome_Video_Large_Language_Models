# Awesome_Video_Large_Language_Models

A curated collection of papers on **video large language models**, organized around three research themes:

- **Spatiotemporal representations:** encoding objects, motion, state changes, and event relationships for understanding and prediction.
- **Efficient long-video understanding:** balancing compression, memory, retrieval, and streaming computation while preserving useful evidence.
- **Grounded video reasoning:** using spatial and temporal anchors, intermediate steps, active observation, and learned feedback to support reliable answers.

The collection also covers model architectures, audio-visual and omni models, training data, post-training, and evaluation, with selected foundational work on visual alignment and motion representation.

## Contents

- [Surveys](#surveys)
- [Representation Learning and Cross-Modal Alignment](#representation)
- [Model Architectures and General Video Understanding](#architecture)
- [Audio-Visual Fusion and Omni Models](#omni)
- [Long-Video Compression and Computational Efficiency](#efficiency)
- [Memory, Retrieval, and Streaming Understanding](#memory)
- [Spatiotemporal Grounding, Reasoning, and Agents](#grounding-reasoning)
- [Data Construction and Training Recipes](#data-training)
- [Reinforcement Learning and Post-Training](#reinforcement-learning)
- [Benchmarks and Diagnostic Evaluation](#evaluation)
- [Related Work: Motion Representation and Generation](#motion-generation)

<a id="surveys"></a>

## Surveys

Overviews of video-language models, training strategies, reasoning, and efficiency.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Why Is Video Still So Expensive? A Survey of Inference-Efficiency Mechanisms in Video and Audiovisual LLMs](https://arxiv.org/abs/2609.10355) | — | 2026-09 | Preprint | [Resources](https://github.com/momentslab/awesome-efficient-videollm) | Inference costs across inputs, encoders, connectors, and language-model execution |
| [Watch, Remember, Reason: Human-View Video Understanding with MLLMs](https://arxiv.org/abs/2606.07433) | — | 2026-06 | Preprint | [Resources](https://github.com/marinero4972/Awesome-HumanView-VideoUnderstanding) | Video understanding through observation, memory, and reasoning |
| [Video-LMM Post-Training: A Deep Dive into Video Reasoning with Large Multimodal Models](https://arxiv.org/abs/2510.05034) | — | 2025-10 | Preprint | [Resources](https://github.com/yoloytang/Awesome-Video-LMM-Post-Training) | Supervised fine-tuning; reinforcement learning; test-time scaling |
| [Video-Language Understanding: A Survey from Model Architecture, Model Training, and Data Perspectives](https://arxiv.org/abs/2406.05615) | — | 2024-06 | [Findings of ACL 2024](https://aclanthology.org/2024.findings-acl.217/) | [Resources](https://github.com/nguyentthong/video-language-understanding) | Video-language understanding through architectures, training strategies, and data |
| [MM-LLMs: Recent Advances in MultiModal Large Language Models](https://arxiv.org/abs/2401.13601) | — | 2024-01 | [Findings of ACL 2024](https://aclanthology.org/2024.findings-acl.738/) | [Resources](https://mm-llms.github.io/) | Multimodal modules and training stages; model taxonomy and training recipes |
| [Video Understanding With Large Language Models: A Survey](https://arxiv.org/abs/2312.17432) | — | 2023-12 | [TCSVT 2026](https://ieeexplore.ieee.org/document/10982110/) | [Resources](https://github.com/yoloytang/Awesome-LLMs-for-Video-Understanding) | Taxonomy of video analyzers, embedders, and LLM roles |

<a id="representation"></a>

## Representation Learning and Cross-Modal Alignment

Visual semantics, motion, temporal relationships, and predictive representations.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [H-JEPA: End-to-End Learning of Hierarchical World Models for Visual Planning](https://arxiv.org/abs/2610.06805) | [H-JEPA](https://huggingface.co/jepa-world-models/h-jepa) | 2026-10 | Preprint | [Code](https://github.com/kevinghst/H-JEPA) | Latent-state prediction across temporal scales for hierarchical planning |
| [V-JEPA 2.1: Unlocking Dense Features in Video Self-Supervised Learning](https://arxiv.org/abs/2603.14482) | [V-JEPA 2.1](https://github.com/facebookresearch/vjepa2#v-jepa-21-pretrained-checkpoints) | 2026-03 | Preprint | [Code](https://github.com/facebookresearch/vjepa2) | Dense prediction losses; intermediate-layer supervision for spatiotemporal features |
| [InternVideo-Next: Towards World-Understanding Video Models](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_InternVideo-Next_Towards_World-Understanding_Video_Models_CVPR_2026_paper.html) | [InternVideo-Next](https://huggingface.co/collections/OpenGVLab/internvideo-next) | 2025-12 | [CVPR 2026](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_InternVideo-Next_Towards_World-Understanding_Video_Models_CVPR_2026_paper.html) | [Code](https://github.com/OpenGVLab/InternVideo/tree/main/InternVideo-Next) | Reconstruction and latent prediction; preserving visual detail and semantics |
| [VL-JEPA: Joint Embedding Predictive Architecture for Vision-language](https://arxiv.org/abs/2512.10942) | VL-JEPA | 2025-12 | [ICLR 2026](https://proceedings.iclr.cc/paper_files/paper/2026/hash/9144aded4e536bc5fb7bfc660a2d7a3d-Abstract-Conference.html) | — | Predicting text semantic embeddings; decoding words only when needed |
| [V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning](https://arxiv.org/abs/2506.09985) | [V-JEPA 2](https://huggingface.co/collections/facebook/v-jepa-2) | 2025-06 | Preprint | [Code](https://github.com/facebookresearch/vjepa2) · [Project](https://ai.meta.com/research/vjepa/) | Masked latent prediction; action-conditioned post-training for planning |
| [InternVideo2: Scaling Foundation Models for Multimodal Video Understanding](https://arxiv.org/abs/2403.15377) | [InternVideo2](https://huggingface.co/collections/OpenGVLab/internvideo2) | 2024-03 | [ECCV 2024](https://link.springer.com/chapter/10.1007/978-3-031-73013-9_23) | [Code](https://github.com/OpenGVLab/InternVideo/tree/main/InternVideo2) | Staged masked video modeling, cross-modal contrastive learning, and text generation |
| [Long-Form Video-Language Pre-Training with Multimodal Temporal Contrastive Learning](https://arxiv.org/abs/2210.06031) | [LF-VILA](https://github.com/microsoft/XPretrain/tree/main/LF-VILA#prepare-data-and-pretrained-model) | 2022-10 | [NeurIPS 2022](https://papers.nips.cc/paper_files/paper/2022/hash/f8290ccc2905538be1a7f7914ccef629-Abstract-Conference.html) | [Code](https://github.com/microsoft/XPretrain/tree/main/LF-VILA) | Temporal contrastive alignment; hierarchical window attention for long-range dependencies |
| [BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation](https://proceedings.mlr.press/v162/li22n.html) | [BLIP](https://github.com/salesforce/BLIP#pre-trained-checkpoints) | 2022-01 | [ICML 2022](https://proceedings.mlr.press/v162/li22n.html) | [Code](https://github.com/salesforce/BLIP) | Caption generation and filtering; joint vision-language understanding and generation |
| [CLIP2Video: Mastering Video-Text Retrieval via Image CLIP](https://arxiv.org/abs/2106.11097) | [CLIP2Video](https://github.com/CryhanFang/CLIP2Video#test-model) | 2021-06 | Preprint | [Code](https://github.com/CryhanFang/CLIP2Video) | Temporal differences and alignment; adapting image CLIP for video–text retrieval |
| [Learning Transferable Visual Models From Natural Language Supervision](https://proceedings.mlr.press/v139/radford21a.html) | [CLIP](https://github.com/openai/CLIP#api) | 2021-02 | [ICML 2021](https://proceedings.mlr.press/v139/radford21a.html) | [Code](https://github.com/openai/CLIP) · [Project](https://openai.com/index/clip/) | Contrastive image–text alignment; text-prompted zero-shot recognition |

<a id="architecture"></a>

## Model Architectures and General Video Understanding

Visual encoders, connectors, cross-attention, and unified multimodal architectures.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Qwen3.5: Towards Native Multimodal Agents](https://qwen.ai/blog?id=qwen3.5) | [Qwen3.5](https://huggingface.co/Qwen/Qwen3.5-397B-A17B) | 2026-02 | Official release | [Repository](https://github.com/QwenLM/Qwen3.5) · [Overview](https://qwen.ai/blog?id=qwen3.5) | Native multimodal joint training; gated linear attention and sparse experts |
| [Qwen3-VL Technical Report](https://arxiv.org/abs/2511.21631) | [Qwen3-VL](https://huggingface.co/collections/Qwen/qwen3-vl) | 2025-11 | Preprint | [Code](https://github.com/QwenLM/Qwen3-VL) · [Project](https://qwen.ai/blog?id=99f0335c4ad9ff6153e517418d48535ab6d8afef) | Multilayer visual feature injection; text timestamps for video grounding |
| [Qwen2.5-VL Technical Report](https://arxiv.org/abs/2502.13923) | [Qwen2.5-VL](https://huggingface.co/Qwen/Qwen2.5-VL-7B-Instruct) | 2025-02 | Preprint | [Code](https://github.com/QwenLM/Qwen2.5-VL) · [Project](https://qwenlm.github.io/blog/qwen2.5-vl/) | Dynamic frame rates; absolute temporal encoding; efficient window attention |
| [Qwen2-VL: Enhancing Vision-Language Model's Perception of the World at Any Resolution](https://arxiv.org/abs/2409.12191) | [Qwen2-VL](https://huggingface.co/Qwen/Qwen2-VL-7B-Instruct) | 2024-09 | Preprint | [Code](https://github.com/QwenLM/Qwen2-VL) · [Project](https://qwenlm.github.io/blog/qwen2-vl/) | Dynamic visual resolution; multimodal rotary position embeddings |
| [LLaVA-OneVision: Easy Visual Task Transfer](https://arxiv.org/abs/2408.03326) | [LLaVA-OneVision](https://huggingface.co/lmms-lab/llava-onevision-qwen2-7b-ov) | 2024-08 | [TMLR 2025](https://openreview.net/forum?id=zKv8qULV6n) | [Code](https://github.com/LLaVA-VL/LLaVA-NeXT) · [Project](https://llava-vl.github.io/blog/2024-08-05-llava-onevision/) | Unified single-image, multi-image, and video training; cross-task transfer |
| [Video-ChatGPT: Towards Detailed Video Understanding via Large Vision and Language Models](https://arxiv.org/abs/2306.05424) | [Video-ChatGPT](https://huggingface.co/MBZUAI/Video-ChatGPT-7B) | 2023-06 | [ACL 2024](https://aclanthology.org/2024.acl-long.679/) | [Code](https://github.com/mbzuai-oryx/Video-ChatGPT) · [Project](https://mbzuai-oryx.github.io/Video-ChatGPT/) | Spatiotemporal feature aggregation; video instruction tuning for open-ended dialogue |
| [VideoChat: chat-centric video understanding](https://arxiv.org/abs/2305.06355) | VideoChat | 2023-05 | [Sci. China Inf. Sci. 2025](https://link.springer.com/article/10.1007/s11432-024-4321-9) | [Code](https://github.com/OpenGVLab/Ask-Anything) | Learnable video–LLM interface; video dialogue instruction tuning |
| [Visual Instruction Tuning](https://arxiv.org/abs/2304.08485) | [LLaVA v0 (delta)](https://huggingface.co/liuhaotian/LLaVA-7b-delta-v0) | 2023-04 | [NeurIPS 2023](https://papers.neurips.cc/paper_files/paper/2023/hash/6dcf277ea32ce3288914faf369fe6de0-Abstract-Conference.html) | [Code](https://github.com/haotian-liu/LLaVA) · [Project](https://llava-vl.github.io/) | Visual feature projection; generative visual instruction tuning |
| [BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models](https://arxiv.org/abs/2301.12597) | [BLIP-2](https://huggingface.co/Salesforce/blip2-opt-2.7b) | 2023-01 | [ICML 2023](https://proceedings.mlr.press/v202/li23q.html) | [Code](https://github.com/salesforce/LAVIS) · [Project](https://github.com/salesforce/LAVIS/tree/main/projects/blip2) | Two-stage Q-Former training; frozen vision and language backbones |
| [Flamingo: a Visual Language Model for Few-Shot Learning](https://arxiv.org/abs/2204.14198) | Flamingo | 2022-04 | [NeurIPS 2022](https://proceedings.neurips.cc/paper_files/paper/2022/hash/960a172bc7fbf0177ccccbb411a7d800-Abstract-Conference.html) | [Overview](https://deepmind.google/blog/tackling-multiple-tasks-with-a-single-visual-language-model/) | Visual resampling; gated cross-attention; multimodal few-shot learning |
| [Multimodal Few-Shot Learning with Frozen Language Models](https://arxiv.org/abs/2106.13884) | Frozen | 2021-06 | [NeurIPS 2021](https://proceedings.neurips.cc/paper_files/paper/2021/hash/01b7575c38dac42f3cfb7d500438b875-Abstract.html) | [Project](https://fh295.github.io/frozen.html) | Frozen language model; trainable image encoder producing continuous visual prefixes |

<a id="omni"></a>

## Audio-Visual Fusion and Omni Models

Audio-visual understanding, multimodal inputs, speech generation, and real-time interaction.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Qwen3.5-Omni Technical Report](https://arxiv.org/abs/2604.15804) | Qwen3.5-Omni · [API](https://help.aliyun.com/zh/model-studio/qwen-omni) | 2026-04 | Preprint | — | Hybrid-attention MoE; dynamic text–speech alignment; long audiovisual interaction |
| [MiniCPM-o 4.5: Towards Real-Time Full-Duplex Omni-Modal Interaction](https://arxiv.org/abs/2604.27393) | [MiniCPM-o 4.5](https://huggingface.co/openbmb/MiniCPM-o-4_5) | 2026-04 | Preprint | [Code](https://github.com/OpenBMB/MiniCPM-V) · [Project](https://openbmb.github.io/minicpm-o-4_5-omni/) | Continuous audiovisual input and speech output within synchronized time slices; full-duplex interaction |
| [Nemotron 3 Nano Omni: Efficient and Open Multimodal Intelligence](https://arxiv.org/abs/2604.24954) | [Nemotron 3 Nano Omni](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16) | 2026-04 | Technical report | [Code](https://github.com/NVIDIA-NeMo/Nemotron) · [Overview](https://developer.nvidia.com/blog/nvidia-nemotron-3-nano-omni-powers-multimodal-agent-reasoning-in-a-single-efficient-open-model/) | Early temporal fusion; visual compression; unified video, audio, and text understanding |
| [Qwen3-Omni Technical Report](https://arxiv.org/abs/2509.17765) | [Qwen3-Omni](https://huggingface.co/collections/Qwen/qwen3-omni) | 2025-09 | Preprint | [Code](https://github.com/QwenLM/Qwen3-Omni) · [Project](https://qwen.ai/blog?id=65f766fc2dcba7905c1cb69cc4cab90e94126bf4) | Thinker–Talker architecture; audiovisual understanding and streaming speech generation |
| [VideoLLaMA 2: Advancing Spatial-Temporal Modeling and Audio Understanding in Video-LLMs](https://arxiv.org/abs/2406.07476) | [VideoLLaMA2-7B (vision)](https://huggingface.co/DAMO-NLP-SG/VideoLLaMA2-7B) | 2024-06 | Preprint | [Code](https://github.com/DAMO-NLP-SG/VideoLLaMA2) | Spatiotemporal convolutional connector; complementary audio branch |
| [Video-LLaMA: An Instruction-tuned Audio-Visual Language Model for Video Understanding](https://arxiv.org/abs/2306.02858) | [Video-LLaMA](https://huggingface.co/DAMO-NLP-SG/Video-LLaMA-Series) | 2023-06 | [EMNLP 2023 Demo](https://aclanthology.org/2023.emnlp-demo.49/) | [Code](https://github.com/DAMO-NLP-SG/Video-LLaMA) | Separate video and audio Q-Formers; alignment with a frozen LLM |
| [VAST: A Vision-Audio-Subtitle-Text Omni-Modality Foundation Model and Dataset](https://arxiv.org/abs/2305.18500) | [VAST](https://drive.google.com/file/d/1ZkeZpis2Fggy4MyTFPqQj37MgPZxdJ53/view) | 2023-05 | [NeurIPS 2023](https://proceedings.neurips.cc/paper_files/paper/2023/hash/e6b2b48b5ed90d07c305932729927781-Abstract-Conference.html) | [Code](https://github.com/CASIA-IVA-Lab/VAST) | Vision–audio–subtitle–text alignment; multimodal video captioning data |

<a id="efficiency"></a>

## Long-Video Compression and Computational Efficiency

Token compression, hierarchical summaries, adaptive sampling, and long-context computation.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Small Vision-Language Models are Smart Compressors for Long Video Understanding](https://arxiv.org/abs/2604.08120) | [Tempo](https://huggingface.co/Vision-CAIR/Tempo-6B) | 2026-04 | [ECCV 2026](https://link.springer.com/chapter/10.1007/978-3-032-37189-8_8) | [Code](https://github.com/FeiElysia/Tempo) · [Project](https://feielysia.github.io/tempo-page/) | Small VLMs compress local video by query and dynamically allocate token budgets |
| [LongVU: Spatiotemporal Adaptive Compression for Long Video-Language Understanding](https://arxiv.org/abs/2410.17434) | [LongVU](https://huggingface.co/Vision-CAIR/LongVU_Qwen2_7B) | 2024-10 | [ICML 2025](https://proceedings.mlr.press/v267/shen25j.html) | [Code](https://github.com/Vision-CAIR/LongVU) · [Project](https://vision-cair.github.io/LongVU/) | Temporal deduplication, query-aware resolution allocation, and spatial compression |
| [LongVILA: Scaling Long-Context Visual Language Models for Long Videos](https://arxiv.org/abs/2408.10188) | [LongVILA](https://huggingface.co/Efficient-Large-Model/qwen2-7b-longvila-1M) | 2024-08 | [ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/2e163450c1ae3167832971e6da29f38d-Abstract-Conference.html) | [Code](https://github.com/NVlabs/VILA/tree/main/longvila) · [Project](https://hanlab.mit.edu/projects/longvila) | Context extension and multimodal sequence parallelism for densely sampled long videos |
| [VideoTree: Adaptive Tree-based Video Representation for LLM Reasoning on Long Videos](https://arxiv.org/abs/2405.19209) | VideoTree | 2024-05 | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_VideoTree_Adaptive_Tree-based_Video_Representation_for_LLM_Reasoning_on_Long_CVPR_2025_paper.pdf) | [Code](https://github.com/Ziyang412/VideoTree) · [Project](https://videotree2024.github.io/) | Query-guided expansion of video cluster trees; keyframe captions for reasoning |
| [Video ReCap: Recursive Captioning of Hour-Long Videos](https://arxiv.org/abs/2402.13250) | [Video ReCap](https://drive.google.com/drive/folders/1q-A3YYB1VaZ9JQqe49UwVja-f-r6HJZJ) | 2024-02 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Islam_Video_ReCap_Recursive_Captioning_of_Hour-Long_Videos_CVPR_2024_paper.html) | [Code](https://github.com/md-mohaiminul/VideoRecap) · [Project](https://sites.google.com/view/vidrecap) | Recursive captioning; hierarchical summaries from clip descriptions and sparse visual features |
| [LLaMA-VID: An Image is Worth 2 Tokens in Large Language Models](https://arxiv.org/abs/2311.17043) | [LLaMA-VID](https://huggingface.co/YanweiLi/llama-vid-7b-full-224-long-video) | 2023-11 | [ECCV 2024](https://link.springer.com/chapter/10.1007/978-3-031-72952-2_19) | [Code](https://github.com/JIA-Lab-research/LLaMA-VID) · [Project](https://llama-vid.github.io/) | Per-frame compression into instruction-relevant context tokens and content tokens |

<a id="memory"></a>

## Memory, Retrieval, and Streaming Understanding

Persistent memory, evidence retrieval, and reuse of historical video computation.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [VideoRAG: Retrieval-Augmented Generation with Extreme Long-Context Videos](https://arxiv.org/abs/2502.01549) | VideoRAG | 2025-02 | [KDD 2026](https://doi.org/10.1145/3770854.3783944) | [Code](https://github.com/HKUDS/VideoRAG) | Text graph indexing and video retrieval; revisiting relevant clips for answer evidence |
| [Streaming Video Question-Answering with In-context Video KV-Cache Retrieval](https://arxiv.org/abs/2503.00540) | ReKV | 2025-01 | [ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/67a9b444cbcd647572c88194619f72d5-Abstract-Conference.html) | [Code](https://github.com/Becomebright/ReKV) | Query-based retrieval of historical KV caches to reuse streaming video computation |
| [ReWind: Understanding Long Videos with Instructed Learnable Memory](https://arxiv.org/abs/2411.15556) | ReWind | 2024-11 | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Diko_ReWind_Understanding_Long_Videos_with_Instructed_Learnable_Memory_CVPR_2025_paper.html) | [Project](https://anxhelodiko.dev/publication/3.rewind/) | Instruction-guided compact memory reads and writes; high-resolution keyframe selection for details |
| [MA-LMM: Memory-Augmented Large Multimodal Model for Long-Term Video Understanding](https://arxiv.org/abs/2404.05726) | [MA-LMM](https://drive.google.com/file/d/1mq6fg69Ofm32-1HjEunoFtPg8ymAIcOp/view) | 2024-04 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/He_MA-LMM_Memory-Augmented_Large_Multimodal_Model_for_Long-Term_Video_Understanding_CVPR_2024_paper.html) | [Code](https://github.com/boheumd/MA-LMM) · [Project](https://boheumd.github.io/MA-LMM/) | Visual and query memories retain history; similar-token merging limits memory size |

<a id="grounding-reasoning"></a>

## Spatiotemporal Grounding, Reasoning, and Agents

Temporal localization, spatial anchors, intermediate reasoning, and active observation.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Open-o3-Video-v2: Seek, Ground, and Reason with Verifiable Spatio-Temporal Evidence](https://arxiv.org/abs/2610.17656) | [Open-o3-Video-v2](https://modelscope.cn/models/FDUBay/Open-o3-Video-v2-4B) | 2026-10 | Preprint | [Code](https://github.com/Multimedia-Semantic-Analytics-Lab/Open-o3-Video-v2) · [Project](https://msalab-pku.github.io/projects/Open-o3-Video-v2) | Tool-based video revisiting for evidence; clue-gain rewards for active reasoning |
| [Thinking With Bounding Boxes: Enhancing Spatio-Temporal Video Grounding via Reinforcement Fine-Tuning](https://arxiv.org/abs/2511.21375) | STVG-o1 | 2025-11 | Preprint | — | Bounding-box chain of thought and geometric rewards for spatiotemporal grounding |
| [Open-o3-Video: Grounded Video Reasoning with Explicit Spatio-Temporal Evidence](https://arxiv.org/abs/2510.20579) | [Open-o3-Video](https://huggingface.co/marinero4972/Open-o3-Video) | 2025-10 | [ICML 2026](https://proceedings.mlr.press/v306/meng26e.html) | [Code](https://github.com/marinero4972/Open-o3-Video) · [Project](https://marinero4972.github.io/projects/Open-o3-Video/) | Explicit timestamps and bounding boxes in reasoning; supervised and reinforcement learning |
| [VideoMind: A Chain-of-LoRA Agent for Temporal-Grounded Video Reasoning](https://arxiv.org/abs/2503.13444) | [VideoMind](https://huggingface.co/collections/yeliudev/videomind) | 2025-03 | [ICLR 2026](https://videomind.github.io/) | [Code](https://github.com/yeliudev/VideoMind) · [Project](https://videomind.github.io/) | Shared backbone with switchable LoRA roles for grounding, verification, and answering |
| [TRACE: Temporal Grounding Video LLM via Causal Event Modeling](https://arxiv.org/abs/2410.05643) | [TRACE](https://huggingface.co/Yongxin-Guo/trace) | 2024-10 | [ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/df027cf11469e746ef94d583f9f5537f-Abstract-Conference.html) | [Code](https://github.com/gyxxyg/TRACE) | Autoregressive interleaving of timestamps, saliency scores, and event captions |
| [VideoAgent: Long-Form Video Understanding with Large Language Model as Agent](https://arxiv.org/abs/2403.10517) | VideoAgent | 2024-03 | [ECCV 2024](https://link.springer.com/chapter/10.1007/978-3-031-72989-8_4) | [Code](https://github.com/wxh1996/VideoAgent) · [Project](https://wxh1996.github.io/VideoAgent-Website/) | Iterative retrieval-query generation and keyframe revisiting for long-video question answering |
| [TimeChat: A Time-sensitive Multimodal Large Language Model for Long Video Understanding](https://arxiv.org/abs/2312.02051) | [TimeChat](https://huggingface.co/ShuhuaiRen/TimeChat-7b) | 2023-12 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Ren_TimeChat_A_Time-sensitive_Multimodal_Large_Language_Model_for_Long_Video_CVPR_2024_paper.html) | [Code](https://github.com/RenShuhuai-Andy/TimeChat) | Timestamp-aware encoding; sliding-window Q-Former for temporal grounding |
| [VTimeLLM: Empower LLM to Grasp Video Moments](https://arxiv.org/abs/2311.18445) | VTimeLLM | 2023-11 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Huang_VTimeLLM_Empower_LLM_to_Grasp_Video_Moments_CVPR_2024_paper.html) | [Code](https://github.com/huangb23/VTimeLLM) | Three-stage boundary-aware training; event localization and description |

<a id="data-training"></a>

## Data Construction and Training Recipes

Caption and instruction datasets, data mixtures, parameter updates, and controlled training studies.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Apollo: An Exploration of Video Understanding in Large Multimodal Models](https://arxiv.org/abs/2412.10360) | Apollo | 2024-12 | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Zohar_Apollo__An_Exploration_of_Video_Understanding_in_Large_Multimodal_CVPR_2025_paper.html) | [Project](https://apollo-lmms.github.io/) | Controlled comparisons of sampling, encoders, data mixtures, and unfreezing schedules |
| [LLaVA-Video: Video Instruction Tuning With Synthetic Data](https://arxiv.org/abs/2410.02713) | [LLaVA-Video](https://huggingface.co/lmms-lab/LLaVA-Video-7B-Qwen2) | 2024-10 | [TMLR 2025](https://openreview.net/forum?id=EELFGut39K) | [Code](https://github.com/LLaVA-VL/LLaVA-NeXT) · [Project](https://llava-vl.github.io/blog/2024-09-30-llava-video/) | Synthetic fine-grained captions and question–answer pairs for video instruction tuning |
| [Vript: A Video Is Worth Thousands of Words](https://arxiv.org/abs/2406.06040) | [Vriptor](https://huggingface.co/Mutonix/Vriptor-STLLM) | 2024-06 | [NeurIPS 2024 D&B](https://papers.nips.cc/paper_files/paper/2024/hash/6903a5aaece71b76623245fc6e32f01b-Abstract-Datasets_and_Benchmarks_Track.html) | [Code](https://github.com/mutonix/Vript) | Dense video scripts covering scene content and camera motion |
| [ShareGPT4Video: Improving Video Understanding and Generation with Better Captions](https://arxiv.org/abs/2406.04325) | [ShareGPT4Video-8B](https://huggingface.co/Lin-Chen/sharegpt4video-8b) | 2024-06 | [NeurIPS 2024 D&B](https://papers.nips.cc/paper_files/paper/2024/hash/22a7476e4fd36818777c47e666f61a41-Abstract-Datasets_and_Benchmarks_Track.html) | [Code](https://github.com/ShareGPT4Omni/ShareGPT4Video) · [Project](https://sharegpt4video.github.io/) | Frame-difference captioning; dense annotations for captioner and video-language model training |
| [MM1: Methods, Analysis and Insights from Multimodal LLM Pre-training](https://arxiv.org/abs/2403.09611) | MM1 | 2024-03 | [ECCV 2024](https://link.springer.com/chapter/10.1007/978-3-031-73397-0_18) | [Project](https://machinelearning.apple.com/research/mm1-methods-analysis-insights) | Visual encoder, connector, and data-mixture ablations for multimodal pretraining |
| [Panda-70M: Captioning 70M Videos with Multiple Cross-Modality Teachers](https://arxiv.org/abs/2402.19479) | — | 2024-02 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Chen_Panda-70M_Captioning_70M_Videos_with_Multiple_Cross-Modality_Teachers_CVPR_2024_paper.html) | [Code](https://github.com/snap-research/Panda-70M) · [Project](https://snap-research.github.io/Panda-70M/) | Multimodal teacher captions; retrieval-based filtering of 70M video–text pairs |
| [VILA: On Pre-training for Visual Language Models](https://arxiv.org/abs/2312.07533) | [VILA](https://huggingface.co/Efficient-Large-Model/VILA-7b) | 2023-12 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Lin_VILA_On_Pre-training_for_Visual_Language_Models_CVPR_2024_paper.html) | [Code](https://github.com/NVlabs/VILA) · [Project](https://hanlab.mit.edu/projects/vila) | Interleaved image–text pretraining; joint LLM updates; multi-image in-context learning |

<a id="reinforcement-learning"></a>

## Reinforcement Learning and Post-Training

Rewards for localization, temporal reasoning, evidence verification, and answer consistency.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [VideoTrace-R1: Long Video-based Retrieval-Augmented Generation via Reinforcement Learning](https://proceedings.mlr.press/v306/cao26m.html) | VideoTrace-R1 | 2026-07 | [ICML 2026](https://proceedings.mlr.press/v306/cao26m.html) | — | Temporal event indexing; stepwise verification rewards; temporally enhanced GRPO |
| [Video-R2: Reinforcing Consistent and Grounded Reasoning in Multimodal Language Models](https://arxiv.org/abs/2511.23478) | [Video-R2](https://huggingface.co/MBZUAI/Video-R2) | 2025-11 | Preprint | [Code](https://github.com/mbzuai-oryx/Video-R2) | Timestamp supervision and temporal alignment rewards for reasoning–answer consistency |
| [Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding](https://arxiv.org/abs/2503.13377) | [Time-R1](https://huggingface.co/collections/Boshenxx/time-r1) | 2025-03 | [NeurIPS 2025](https://proceedings.neurips.cc/paper_files/paper/2025/hash/7801b29c93b599b8d0c44138596bdeed-Abstract-Conference.html) | [Code](https://github.com/xiaomi-research/Time-R1) · [Project](https://xuboshen.github.io/Time-R1/) | Temporal grounding rewards and progressive sample filtering for video segment localization |
| [Video-R1: Reinforcing Video Reasoning in MLLMs](https://arxiv.org/abs/2503.21776) | [Video-R1](https://huggingface.co/Video-R1/Video-R1-7B) | 2025-03 | [NeurIPS 2025](https://proceedings.neurips.cc/paper_files/paper/2025/hash/8eb3976840e08b80dda9667562574246-Abstract-Conference.html) | [Code](https://github.com/tulerfeng/Video-R1) | Temporal rewards and mixed image-video data for reinforcement learning of video reasoning |

<a id="evaluation"></a>

## Benchmarks and Diagnostic Evaluation

Perception, temporal reasoning, grounding, hallucination, instruction following, and online interaction.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [Video-HolmesV2: Can MLLMs Reason with Spatio-Temporal Audio-Visual Evidence in Long Videos?](https://arxiv.org/abs/2609.17248) | — | 2026-09 | [ECCV 2026](https://link.springer.com/chapter/10.1007/978-3-032-36987-1_33) | — | Long-video audiovisual coupling; spatiotemporal evidence localization and scoring |
| [Video-IFBench: Evaluating Instruction Following of Multimodal LLMs in Video Understanding Scenarios](https://arxiv.org/abs/2608.25529) | — | 2026-08 | Preprint | [Code](https://github.com/Alexios-hub/Video-IFBench) · [Project](https://alexios-hub.github.io/Video-IFBench/) | Video instruction following; multiple tasks, conditional choices, and nested constraints |
| [Video-MME-v2: Towards the Next Stage in Benchmarks for Comprehensive Video Understanding](https://arxiv.org/abs/2604.05015) | Video-MME-v2 (benchmark) | 2026-04 | Preprint | [Code](https://github.com/MME-Benchmarks/Video-MME-v2) · [Project](https://video-mme-v2.netlify.app/) | Hierarchical assessment of information aggregation, temporal understanding, and reasoning consistency |
| [Breaking Down Video LLM Benchmarks: Knowledge, Spatial Perception, or True Temporal Understanding?](https://arxiv.org/abs/2505.14321) | VBenchComp (diagnostic framework) | 2025-05 | [NeurIPS 2025 Workshop: Evaluating the Evolving LLM Lifecycle](https://machinelearning.apple.com/research/breaking-down) | [Project](https://machinelearning.apple.com/research/breaking-down) | Video removal and frame-shuffling controls; separating knowledge, static semantics, and temporal understanding |
| [SVBench: A Benchmark with Temporal Multi-Turn Dialogues for Streaming Video Understanding](https://arxiv.org/abs/2502.10810) | StreamingChat | 2025-02 | [ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/693ce820ea7e0f0c70a2a833cbdf7ccc-Abstract-Conference.html) | [Code](https://github.com/sotayang/SVBench) · [Project](https://sotayang.github.io/SVBench/) | Streaming multi-turn question chains; dialogue across time intervals; StreamingChat |
| [OVO-Bench: How Far is Your Video-LLMs from Real-World Online Video Understanding?](https://arxiv.org/abs/2501.05510) | — | 2025-01 | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Niu_OVO-Bench_How_Far_is_Your_Video-LLMs_from_Real-World_Online_Video_CVPR_2025_paper.html) | [Code](https://github.com/JoeLeelyf/OVO-Bench) · [Project](https://joeleelyf.github.io/OVO-Bench/) | Retrospective review; real-time perception; active responses after waiting for subsequent evidence |
| [TemporalBench: Benchmarking Fine-grained Temporal Understanding for Multimodal Video Models](https://arxiv.org/abs/2410.10818) | — | 2024-10 | [NeurIPS 2024 Workshop on Video-Language Models](https://openreview.net/forum?id=bhuZn4URBH) | [Code](https://github.com/mu-cai/TemporalBench) · [Project](https://temporalbench.github.io/) | Fine-grained motion descriptions; repetition counts, magnitude, and order; MBA scoring |
| [LongVideoBench: A Benchmark for Long-context Interleaved Video-Language Understanding](https://arxiv.org/abs/2407.15754) | — | 2024-07 | [NeurIPS 2024 D&B](https://proceedings.neurips.cc/paper_files/paper/2024/hash/329ad516cf7a6ac306f29882e9c77558-Abstract-Datasets_and_Benchmarks_Track.html) | [Code](https://github.com/longvideobench/LongVideoBench) · [Project](https://longvideobench.github.io/) | Interleaved long videos and subtitles; referential cues; detailed retrieval and reasoning |
| [MMBench-Video: A Long-Form Multi-Shot Benchmark for Holistic Video Understanding](https://arxiv.org/abs/2406.14515) | — | 2024-06 | [NeurIPS 2024 D&B](https://proceedings.neurips.cc/paper_files/paper/2024/hash/a2326c9715a516c91174132e0170073a-Abstract-Datasets_and_Benchmarks_Track.html) | [Code](https://github.com/open-compass/VLMEvalKit) · [Project](https://mmbench-video.github.io/) | Long, multi-shot videos; human-annotated open-ended QA; LLM scoring |
| [VideoHallucer: Evaluating Intrinsic and Extrinsic Hallucinations in Large Video-Language Models](https://arxiv.org/abs/2406.16338) | — | 2024-06 | Preprint | [Code](https://github.com/patrick-tssn/VideoHallucer) · [Project](https://videohallucer.github.io/) | Intrinsic and extrinsic hallucinations; adversarial binary question answering |
| [Video-MME: The First-Ever Comprehensive Evaluation Benchmark of Multi-modal LLMs in Video Analysis](https://arxiv.org/abs/2405.21075) | — | 2024-05 | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Fu_Video-MME_The_First-Ever_Comprehensive_Evaluation_Benchmark_of_Multi-modal_LLMs_in_CVPR_2025_paper.html) | [Code](https://github.com/MME-Benchmarks/Video-MME) · [Project](https://video-mme.github.io/) | Short and long videos; audio and subtitles; multidomain multiple-choice questions |
| [TempCompass: Do Video LLMs Really Understand Videos?](https://arxiv.org/abs/2403.00476) | — | 2024-03 | [Findings of ACL 2024](https://aclanthology.org/2024.findings-acl.517/) | [Code](https://github.com/llyx97/TempCompass) | Similar static content with distinct dynamics; temporal perception across question formats |
| [MVBench: A Comprehensive Multi-modal Video Understanding Benchmark](https://arxiv.org/abs/2311.17005) | VideoChat2 | 2023-11 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Li_MVBench_A_Comprehensive_Multi-modal_Video_Understanding_Benchmark_CVPR_2024_paper.html) | [Code](https://github.com/OpenGVLab/Ask-Anything/tree/main/video_chat2) · [Project](https://github.com/OpenGVLab/Ask-Anything/blob/main/video_chat2/MVBENCH.md) | Twenty temporal tasks; multiple-choice questions about video dynamics; VideoChat2 |
| [Can I Trust Your Answer? Visually Grounded Video Question Answering](https://arxiv.org/abs/2309.01327) | NExT-GQA (benchmark) | 2023-09 | [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Xiao_Can_I_Trust_Your_Answer_Visually_Grounded_Video_Question_Answering_CVPR_2024_paper.html) | [Code](https://github.com/doc-doc/NExT-GQA) | Joint evaluation of answers and supporting segments; answer–evidence consistency |
| [EgoSchema: A Diagnostic Benchmark for Very Long-form Video Language Understanding](https://arxiv.org/abs/2308.09126) | — | 2023-08 | [NeurIPS 2023 D&B](https://proceedings.neurips.cc/paper_files/paper/2023/hash/90ce332aff156b910b002ce4e6880dec-Abstract-Datasets_and_Benchmarks.html) | [Code](https://github.com/egoschema/EgoSchema) · [Project](https://egoschema.github.io/) | Long egocentric videos; human-written multiple-choice questions; understanding across segments |

<a id="motion-generation"></a>

## Related Work: Motion Representation and Generation

Explicit and implicit motion representations for animation and controllable generation.

| Paper | Model / Method | Date | Venue | Code / Project | Highlights |
| --- | --- | --- | --- | --- | --- |
| [LivePortrait: Efficient Portrait Animation with Stitching and Retargeting Control](https://arxiv.org/abs/2407.03168) | [LivePortrait](https://huggingface.co/KlingTeam/LivePortrait) | 2024-07 | Preprint | [Code](https://github.com/KlingAIResearch/LivePortrait) · [Project](https://liveportrait.github.io/) | Implicit keypoint motion transfer; stitching and eye/lip retargeting enhance control |
| [X-Portrait: Expressive Portrait Animation with Hierarchical Motion Attention](https://arxiv.org/abs/2403.15931) | [X-Portrait](https://drive.google.com/drive/folders/1Bq0n-w1VT5l99CoaVg02hFpqE5eGLo9O) | 2024-03 | [SIGGRAPH 2024](https://doi.org/10.1145/3641519.3657459) | [Code](https://github.com/bytedance/X-Portrait) · [Project](https://byteaigc.github.io/x-portrait/) | Learned motion control from RGB driving inputs; local attention refines facial expressions |
| [First Order Motion Model for Image Animation](https://arxiv.org/abs/2003.00196) | FOMM | 2019 | [NeurIPS 2019](https://proceedings.neurips.cc/paper/2019/hash/31c0b36aef265d9221af80872ceb62f9-Abstract.html) | [Code](https://github.com/AliaksandrSiarohin/first-order-model) · [Project](https://aliaksandrsiarohin.github.io/first-order-model-website/) | Self-supervised keypoints and local affine transformations for image animation |
