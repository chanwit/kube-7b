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

### Getting Started with Ollama
```
ollama run chanwit/kube-7b:v0.1
```

### Getting Started with Llamafile

Download from: [https://hf.co/chanwit/kube-7b-v0.1-gguf/kube-7b-v0.1.llamafile](https://huggingface.co/chanwit/kube-7b-v0.1-gguf/blob/main/kube-7b-v0.1.llamafile)

Here's the `kube-7b` bash script to run the model with its system prompt.
```shell
(
echo "<|system|>
You are a Kube AI assistant.</s>
<|user|>
"$@"</s>
<|assistant|>"
) | ./kube-7b-v0.1.llamafile -t 8 --temp 0.1 2>/dev/null
```

Save it as `./kube-7b` then run `./kube-7b "What is Kubernetes?"` to try the model.

## Prompt

The models in this collection use the `zephyr` prompt format.

# Contributions

Contributions to this project are greatly appreciated, specifically in the form of question and answer pairs, which will aid in the enhancement of future models. We are actively seeking contributions for a [new dataset centered around knowledge of Kubernetes 1.29](datasets/).
