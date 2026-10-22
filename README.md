# Recursive CLIP: Vision-Language Distillation with Looped Transformer Blocks

**🎉 Accepted at WACV (IEEE/CVF Winter Conference on Applications of Computer Vision)**

This repository contains the official implementation of **Recursive CLIP**, a parameter-efficient vision-language framework that investigates recurrent weight sharing in CLIP architectures.

## 🔍 Overview

Traditional CLIP models rely on independently parameterized transformer blocks across depth. In this work, we explore whether these blocks can be **reused recurrently** while preserving CLIP's powerful vision-language representations and transfer capabilities.

We introduce two recursive CLIP variants:

- **rCLIP:** Applies recurrent transformer blocks exclusively to the vision encoder.
- **r²CLIP:** Extends recurrence to both the vision and text encoders.

By applying a small set of **N transformer blocks M times**, while keeping the total computational depth fixed, our approach substantially reduces the number of distinct parameters without reducing the effective network depth.

We investigate both **contrastive training** and **knowledge distillation** from a strong ViT-B/16 CLIP teacher pretrained on DFN-2B, using the considerably smaller CC3M and CC12M datasets.

## 🚀 Key Highlights

- **Parameter Efficiency:** Reduce model parameters through recurrent transformer block sharing while preserving computational depth.
- **Flexible Recurrence:** Explore weight sharing in the visual encoder alone (rCLIP) or in both visual and textual encoders (r²CLIP).
- **Knowledge Distillation:** Transfer vision-language knowledge from a large-scale pretrained CLIP teacher using smaller datasets.
- **Extensive Evaluation:** Investigate zero-shot image classification, cross-modal retrieval, few-shot learning, visual grounding, and concept unlearning.
- **Transferability:** Demonstrate that CLIP can tolerate substantial block reuse, with performance depending on the encoder and downstream task.

## 📄 Abstract

Contrastive vision-language models such as CLIP typically rely on independently parameterized transformer blocks across depth. We investigate the extent to which these blocks can instead be reused recurrently while preserving the transferable capabilities of CLIP. We study recursive transformer backbones in which a small set of N transformer blocks is applied M times per forward pass. By holding N · M fixed to the depth of a standard ViT-B, our models preserve computational depth while progressively increasing parameter sharing.

We consider two recursive CLIP model families: rCLIP, where only the vision encoder is recursive, and r²CLIP, where recurrence is also introduced in the text encoder. We study these models under both direct contrastive training and through knowledge distillation from a strong ViT-B/16 teacher pretrained on DFN-2B, using the substantially smaller CC3M and CC12M datasets.

We evaluate the resulting models on zero-shot classification and cross-modal retrieval, and further study their adaptability through few-shot learning, visual grounding, and concept unlearning. Our results show that CLIP can tolerate substantial recurrent block reuse, although its effect depends on the encoder and downstream task. Recurrence also provides parameter efficiency by construction, since fewer distinct transformer blocks need to be stored and adapted. Our results establish recurrent block reuse as a practical design space for vision-language models and highlight its implications for knowledge transfer, downstream adaptation, and parameter efficiency.

`

*The complete BibTeX entry will be updated upon publication.*
