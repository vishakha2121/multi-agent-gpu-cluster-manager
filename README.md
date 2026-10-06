<div align="center">

# 🚀 Multi-Agent Autonomous GPU Cluster Manager

### AI-Powered Self-Managing GPU Infrastructure Using Google Gemini

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![Gemini](https://img.shields.io/badge/Gemini_API-1.5_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)
[![SQLite](https://img.shields.io/badge/SQLite-3-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

**A practice-level project simulating an autonomous multi-agent system that manages GPU clusters — scheduling jobs, balancing load, predicting failures, optimizing utilization, and reducing inference costs — all powered by Google Gemini's reasoning capabilities.**

[Overview](#-overview) • [Features](#-features) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Setup](#-installation--setup) • [Usage](#-usage) • [API](#-api-reference) • [Demo](#-demo)

</div>

---

## 📖 Overview

Modern AI companies like **NVIDIA**, **OpenAI**, and **Microsoft** run massive GPU clusters with thousands of nodes. Managing these clusters manually is impossible — you need **autonomous agents** that think, decide, and act.

This project implements a **Multi-Agent Autonomous GPU Cluster Manager** where **5 specialized AI agents** collaborate (via a central orchestrator) to manage a simulated GPU cluster in real time. Each agent uses **Google Gemini API** for reasoning and decision-making, with intelligent **heuristic fallbacks** when the LLM is unavailable.

> ⚠️ **Note:** This is a **practice/learning project**, not a production system. Real GPUs are **simulated** in Python so it runs on any CPU-only laptop.

---

## 🎯 Problem Statement

Managing GPU clusters involves complex, interconnected challenges:

| Challenge | Manual Approach | Our Solution |
|-----------|----------------|--------------|
| **Job Scheduling** | Engineers assign jobs manually | 🤖 Scheduler Agent picks optimal GPU |
| **Load Balancing** | Reactive — after overload | 🤖 Load Balancer Agent rebalances proactively |
| **Failure Prediction** | Only after crash | 🤖 Failure Predictor flags risks early |
| **Utilization** | Often 30-50% idle | 🤖 Optimizer maximizes throughput |
| **Inference Cost** | Grows linearly | 🤖 Cost Agent reduces with batching & routing |

---

## ✨ Features

### 🤖 Multi-Agent Intelligence
- **5 Specialized Agents** — Scheduler, Load Balancer, Failure Predictor, Optimizer, Cost
- **Central Orchestrator** — Coordinates agents, resolves conflicts, broadcasts events
- **Message Bus** — Agents communicate with each other (e.g., Failure Predictor → Scheduler)
- **Gemini-Powered Reasoning** — Every decision has an explainable LLM reasoning trace
- **Heuristic Fallback** — Rule-based algorithms when Gemini is unavailable/slow

### 🖥️ GPU Cluster Simulation
- Simulated NVIDIA A100, H100, V100 nodes
- Realistic utilization, temperature, memory, and power metrics
- Random failure injection (5% probability)
- Auto-generating workloads (training + inference jobs)

### 📊 Real-Time Dashboard
- Live metrics via WebSocket
- Beautiful dark-mode UI (TailwindCSS + shadcn/ui)
- Interactive charts (Recharts)
- Agent decision feed (see what each agent is thinking)
- Failure predictions with risk gauges
- Cost savings tracker

### 🔌 Full REST API
- Clean FastAPI backend
- Auto-generated Swagger docs (`/docs`)
- WebSocket endpoint for live updates

### 🗄️ Persistent Storage
- SQLite database (zero setup)
- SQLAlchemy ORM
- Seed script for demo data

---

## 🏗️ Architecture

### High-Level System Diagram



> Full file structure is documented in [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

---

## 🚀 Installation & Setup

### Prerequisites

- **Python 3.11+** — [Download](https://python.org/downloads)
- **Node.js 18+** and **npm** — [Download](https://nodejs.org)
- **Google Gemini API Key** — [Get free](https://aistudio.google.com/app/apikey)
- **Git** — [Download](https://git-scm.com)

> 💡 **No GPU required** — everything runs on CPU via simulation.

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/multi-agent-gpu-cluster-manager.git
cd multi-agent-gpu-cluster-manager


cd backend

# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (macOS/Linux)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt