# 🌿 HealthPaddie — Multilingual AI Health Assistant

A RAG-based digital companion delivering verified health information in local African languages.

## Overview

HealthPaddie is an AI-powered health assistant designed to provide trusted, verified, and easy-to-understand health information especially for people in rural or underserved communities across Africa.

Built during the DataHER Africa Hackathon 2025 (#DHAD25) https://dataherafrica.org, HealthPaddie helps users ask health-related questions and receive answers grounded in real medical documents (WHO, NCDC, UNICEF).

HealthPaddie stands out with:
- Multilingual support — English, Hausa, Yoruba, Igbo

- Verified medical information — No hallucinations

- Streamlit conversational interface

- Text-to-Speech (TTS) for accessibility

- Groq LLM inference for fast, safe responses

## Find our application live here: https://healthpaddiee.streamlit.app

## Problem Statement

Access to verified medical information remains a challenge for many communities due to:

- Widespread misinformation
- Language barriers
- Lack of trusted sources
- Limited literacy

HealthPaddie provides verified, multilingual health answers in a simple, accessible way.

## Key Features
- Document-Grounded Health Answers (RAG)

- Retrieves facts from a FAISS vectorstore built with curated medical datasets.

- Multilingual Support: 
        Responses available in:
        - English 
        - Hausa 
        - Yoruba 
        - Igbo

- AI-Powered Text-to-Speech

- Enables users with low literacy or visual challenges to hear answers in audio.

- Fast AI Response (Groq LLaMA 3.1)

- Ultra-low latency responses using Groq’s LLM API.

## Safety-First Approach

- No diagnoses

- Encourages medical consultation

- Detects potentially serious symptoms

## Built From
- WHO fact sheets
- American Society for Microsoft 
- National Minority AIDS Council (NMAC)
- Health education PDFs
 - Public medical datasets

## RAG Pipeline Diagram
                      ┌────────────────────────┐
                      │        User Input       │
                      │  (Health question in    │
                      │  English/Hausa/Yoruba/  │
                      │          Igbo)          │
                      └────────────┬───────────┘
                                   │
                                   ▼
                      ┌────────────────────────┐
                      │  Language Instruction   │
                      │  (Custom rules per      │
                      │   selected language)    │
                      └────────────┬───────────┘
                                   │
                                   ▼
                      ┌────────────────────────┐
                      │     Vector Retriever    │
                      │  FAISS + MiniLM         │
                      │  Searches verified      │
                      │  medical documents      │
                      └────────────┬───────────┘
                                   │
                                   ▼
                    ┌────────────────────────────┐
                    │       Retrieved Context     │
                    │  (Top relevant WHO/NCDC     │
                    │     health facts)           │
                    └────────────┬───────────────┘
                                 │
                                 ▼
                    ┌────────────────────────────┐
                    │    RAG Prompt Builder       │
                    │  Combines:                  │
                    │   - System rules            │
                    │   - Chat history            │
                    │   - User question           │
                    │   - Document context        │
                    └────────────┬───────────────┘
                                 │
                                 ▼
                    ┌────────────────────────────┐
                    │        LLM Engine           │
                    │   Groq LLaMA 3.1-8B         │
                    │  Generates safe, grounded   │
                    │       health answers        │
                    └────────────┬───────────────┘
                                 │
                                 ▼
             ┌──────────────────────────────────────────┐
             │        Final Answer to User               │
             │   (Short, safe, verified explanation)    │
             │   Optional: Text-to-Speech playback       │
             └──────────────────────────────────────────┘

## Use Cases
- Community health outreach
- Rural health awareness
- First-aid & symptom education
- Youth-friendly health education
- NGO/clinic support tools

## Limitations
- Not a diagnostic tool
- Answers vary based on dataset quality
- Requires internet for Groq API
- TTS voice availability may differ by language

## Team Members


Nunsi Shiaki — AI/ML integration & RAG logic

Olamide Lawal — Backend development, Streamlit UI, TTS integration

Glory Baigai — Data processing, UX workflow, vectorstore preparation

