# 🎙️ Varsity FC: End-to-End Automated Sports Podcast Pipeline

### **Project Overview**
Varsity FC is a fully automated "Headless Media" pipeline that produces a daily sports podcast without human intervention. The system scrapes real-time data, uses multi-agent AI to write scripts, synthesizes broadcast-quality audio, and publishes episodes to RSS feeds.

**Live Demo:** https://varsityfcrundown.transistor.fm/  
**Video Walkthrough:**https://www.loom.com/share/d524694580894dd3a52312ea6e47d957

---

### 🏗️ Architecture
The pipeline is built on a **Low-Code/Serverless** architecture using **n8n** as the orchestrator.

```mermaid
graph TD
    A[Trigger: 4:00 AM PST] --> B[Data Collector Node]
    B -->|Fetch Scores| C[ESPN & API-Football APIs]
    B -->|Fetch News| D[Jina.ai Scraper]
    C & D --> E[AI Agent: Executive Producer]
    E -->|Select Topics| F[AI Agent: Scriptwriter - Claude 3.5]
    F -->|Generate Audio| G[ElevenLabs API - Multilingual Model]
    G -->|Publish| H[Transistor.fm API]
```
