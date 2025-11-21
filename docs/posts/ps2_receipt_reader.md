---
date: 2025-01-02
image: ./portfolio/p2-1.jpg
type: personal-work
tech_stacks:
    - go
    - grpc
    - cloud-vision
    - gemini
---

# Receipt Reader

Developed a gRPC service that receives receipt images from clients and processes them with Cloud Vision for OCR, especially for Thai receipts where extraction accuracy can vary. The extracted text is then refined using Gemini, which converts it into a structured JSON format and corrects any errors to ensure reliable output. This service is designed to support downstream systems that require accurate receipt data.

<!-- more -->

**github:** [receipt-reader](https://github.com/hifat/receipt-reader)

![w1](/portfolio/p2-1.jpg)
