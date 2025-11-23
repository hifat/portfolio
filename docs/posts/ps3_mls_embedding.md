---
date: 2025-01-03
image: https://static.vecteezy.com/system/resources/previews/021/009/960/non_2x/embed-icon-black-script-icon-programming-coding-linear-icon-illustration-free-vector.jpg
type: personal-work
tech_stacks:
    - go
    - grpc
    - qdrant-db
    - ollama
---

#  Mallow Sale – Product Embedding Service

This service addresses inconsistent product naming across retailers by generating embeddings for product names using paraphrase-multilingual (Ollama) and storing vectors in QdrantDB for efficient similarity search. Clients send product names via gRPC; the service finds the closest embedding and returns the matching Product ID. The result improves POS product mapping accuracy even when names differ between sources.

<!-- more -->

**github:** [mallow-sale-embedding](https://github.com/hifat/mallow-sale-embedding)

![w1](/portfolio/p3-1.png)
