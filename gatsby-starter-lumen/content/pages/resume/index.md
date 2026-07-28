---
title: "Resume"
template: "page"
description: "Jiaming Nie — Founding Software Engineer specializing in applied AI systems"
---

# Jiaming Nie

Founding Software Engineer specializing in applied AI, LLM training and
evaluation, multi-agent systems, and production backend infrastructure.

[Email](mailto:jiaming.nie13@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/jmnie) ·
[GitHub](https://github.com/jmnie)

_Last updated: July 2026._

## Skills

- **AI/ML:** LLM fine-tuning (SFT and RFT), prompt engineering, RAG,
  multi-agent systems, model evaluation, and benchmarking
- **Models and APIs:** OpenAI (GPT-4.1 and o4-mini), Anthropic Claude, and
  Twilio Voice AI
- **Languages:** Python, JavaScript, and TypeScript
- **Frameworks and infrastructure:** FastAPI, React, MongoDB, Redis, Docker,
  AWS, Jenkins CI/CD, and Prometheus/Grafana

## Experience

### Youlify — Remote

**Founding Software Engineer** · January 2025–Present

- Built and operated OpenAI-hosted SFT and RFT workflows for medical billing
  code extraction. Curated office and surgery datasets covering more than
  2,000 encounters, generated practice-stratified training and evaluation
  datasets from clinical notes and PDF-derived documentation, and launched
  GPT-4.1 SFT and o4-mini RFT jobs through the OpenAI Fine-Tuning API.
- Implemented the supporting evaluation stack, including token and cost
  tracking, checkpoint evaluation, benchmark comparisons, and a Python grader
  using weighted edit distance, CPT prefix decay, and ICD/modifier overlap.
- Built production AI workflows for healthcare revenue cycle management,
  including Charge Verifier and Denial Agent, with structured claim context,
  fine-tuned model routing, Redis-backed task state, and asynchronous appeal
  letter generation.
- Developed a Redis-backed WebSocket notification platform that gives users
  real-time visibility into patient and document sync, AI EOB parsing, charge
  verification, denial analysis, and policy monitoring.
- Implemented bidirectional WebSocket proxying for Twilio voice streams and
  server-sent event streaming for AI copilot conversations across portal and
  practice-management products.
- Helped evolve the platform from a monolithic backend into FastAPI services
  spanning practice management, portal, integration, authentication, and GenAI
  capabilities.
- Built and maintained Selenium and Playwright EHR automation for document
  download, patient and encounter sync, and operative-note retrieval across
  systems including Athena and Practice Fusion.

### peerup — Shanghai, China

**Software Engineer** · June 2023–January 2025

- Led backend development for an AI assistant and chatbot in a note-taking
  product using Python and FastAPI.
- Built a RAG system with Milvus and Elasticsearch to retrieve from public,
  private, and third-party knowledge sources.
- Delivered content enrichment features including text segmentation, keyword
  highlighting, and public-reference retrieval.
- Served as a project architect, leading technology selection, system design,
  project planning, CI/CD, containerization, and engineering conventions.

### Oqton — Shanghai, China

**Software Engineer** · October 2021–February 2023

- Developed Flask applications that communicated with industrial machine APIs,
  collected telemetry, and issued commands.
- Deployed and maintained the applications in Docker on Linux gateways.
- Investigated production issues using Elasticsearch and Apache Kafka.
- Built Node.js and Express APIs plus React features for machine configuration,
  filtering, and sorting.

### Micro Focus — Shanghai, China

**Software Engineer** · July 2020–September 2021

- Developed web-component detection features using JavaScript, C++, and object
  recognition.
- Implemented cross-domain element detection for web automation in Node.js.
- Improved the customer-case workflow, reducing average development-stage
  handling time by four days per case.

## Selected Projects

### Medical Billing Code Extraction with LLM Fine-Tuning

**February 2026–Present**

- Fine-tuned GPT-4.1 with SFT and o4-mini with RFT on more than 2,000 clinical
  encounter-to-billing-code pairs across office and surgery domains.
- Designed an RFT reward function using weighted edit distance, CPT prefix
  decay, ICD/modifier Jaccard distance, and exponential scoring.
- Built the pipeline from clinical-note CSV and PDF extraction through CPT,
  ICD-10, and modifier normalization to SFT/RFT JSONL generation, token
  counting, and cost estimation.
- Evaluated CPT, ICD-10, modifier, and full-code accuracy with macro/micro
  precision, recall, and F1 across checkpoints and base models.

### Real-Time Infrastructure for AI Agent Workflows

**January 2025–Present**

- Designed a WebSocket notification layer for multi-stage AI workflows,
  replacing REST polling with real-time task progress.
- Built a Redis Cluster-backed asynchronous task state machine with sub-state
  tracking, notification deduplication, and reliable final-state delivery.
- Implemented server-sent event streaming for AI copilots while persisting
  complete messages to MongoDB and triggering conversation summarization.

### AI Assistant and Chatbot for a Note-Taking Product

**September 2023–January 2025**

- Developed a FastAPI backend for an AI assistant with streaming responses,
  instruction execution, and file-based question answering.
- Built hybrid RAG with Milvus and Elasticsearch across public, private, and web
  sources.
- Implemented agent workflows with LangChain and LlamaIndex and Redis-backed
  conversation, message, attachment, and user-context management.

## Education

### Worcester Polytechnic Institute — Massachusetts, United States

**Master of Science, Computer Science** · August 2017–December 2019

### University of Liverpool — Liverpool, United Kingdom

**Bachelor of Engineering, Electrical Engineering** · August 2015–June 2017

### Xi'an Jiaotong-Liverpool University — Suzhou, China

**Bachelor of Engineering, Electrical Engineering** · August 2013–August 2015
