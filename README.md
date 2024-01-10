# OpenKubeLM

OpenKubeLM is the collection of fine-tuned versions of Mistral 7B, designed to be your Cloud Native assistant.

Our first model in this collection is `kube-7b`.

# kube-7b

`kube-7b` is a model in the OpenKubeLM collections, designed to be your Cloud Native assistant.

This version of `kube-7b` is a fine-tuned version of Mistral 7B, learning from a 10k dataset related to Kubernetes and Cloud Native knowledge. It will answer your questions with Cloud Native context.

## Why OpenKubeLM?

Currently, there is no suitable open-source model for providing assistance with Cloud Native-specific knowledge and context. OpenKubeLM is an effort to fill this gap. We recently achieved this following the release of `Mixtral 8x7B`, using it to synthesize high-quality datasets from public knowledge without relying on ChatGPT or GPT-4 APIs.

We have successfully used Mistral 8x7B to synthesize the initial dataset (`filtered_kube_10k`), which was then used to DPO fine-tune a variant of Mistral 7B. This resulted in `kube-7b`, the first model in our OpenKubeLM collection.

We use the tokenizer from Zephyr and the model is delivered as the GGUFv3 format supported by Ollama, Llamafile, and etc.

## Prompt

The models in this collection use the `zephyr` prompt format.
