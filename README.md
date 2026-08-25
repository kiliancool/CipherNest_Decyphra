# CipherNest_Decyphra

Decyphra

AI-powered blockchain wallet investigation and intelligence

Turn raw blockchain activity into something humans can actually understand.

Decyphra is an experimental AI-powered blockchain investigation platform designed to help users understand what is happening inside a cryptocurrency wallet.

Instead of forcing users to manually interpret transaction hashes, token transfers, hexadecimal data, contract interactions, and unfamiliar blockchain activity, Decyphra combines blockchain data processing with an AI reasoning layer to turn raw on-chain evidence into clear, conversational investigation results.

«Current stage: TRL 3 — Experimental Proof of Concept»

---

The Problem

Blockchain data is public.

Understanding it isn't.

A blockchain explorer can show you transactions, addresses, token movements, timestamps, contract calls and transaction hashes — but raw transparency does not automatically mean usable information.

For many users, investigating a wallet still means jumping between explorers, token pages and transaction records while trying to manually connect the dots.

Questions such as:

- What is this wallet doing?
- Where are its assets moving?
- Which tokens has it interacted with?
- What happened recently?
- Is there anything unusual about this activity?
- What does this transaction actually mean?

can require significant blockchain knowledge to answer.

Decyphra is built around a simple idea:

«Make blockchain activity understandable without hiding the underlying evidence.»

---

What Decyphra Does

At its core, Decyphra follows a simple investigation pipeline:

Wallet Address
      ↓
Blockchain Data
      ↓
Data Extraction
      ↓
Normalization & Parsing
      ↓
Structured Evidence
      ↓
AI Reasoning Layer
      ↓
Human-readable Investigation
      ↓
Follow-up Questions

The AI is not intended to replace the underlying blockchain evidence.

It interprets the evidence that the system retrieves and processes.

---

Core Concept

A user provides a wallet address.

Decyphra retrieves relevant blockchain activity through blockchain APIs and processes the resulting data into information that can be consumed by the AI reasoning layer.

The system can then present information such as:

- Wallet activity
- Native asset balance
- Token holdings
- Token transfers
- Recent transactions
- Transaction history
- Contract interactions
- Relevant transaction metadata
- Patterns within available activity

The AI layer then converts this structured information into a natural-language investigation.

Users can continue the conversation and ask follow-up questions about the wallet rather than repeatedly starting from raw blockchain data.

---

Evidence First

One of the core design principles behind Decyphra is:

«Evidence is the foundation of the investigation.»

The system should distinguish between:

What the blockchain data demonstrates

and

What the AI believes may be happening.

Decyphra is therefore designed around an evidence-first approach rather than allowing the AI to freely speculate about blockchain activity.

This distinction becomes increasingly important as the system develops more advanced investigative capabilities.

---

Current PoC Architecture

The current prototype is modular so that the blockchain, parsing, and AI layers can evolve independently.

                    ┌──────────────────┐
                    │      User        │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Application      │
                    │ Entry Point      │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Blockchain/API   │
                    │ Data Retrieval   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Parser /         │
                    │ Normalizer       │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Structured       │
                    │ Evidence         │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ AI Reasoning     │
                    │ Layer            │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Investigation    │
                    │ Results          │
                    └──────────────────┘

---

AI Layer

The AI subsystem is responsible for the reasoning and conversational component of Decyphra.

The current implementation separates responsibilities across several modules.

ai/
├── engine.py
├── api.py
├── config.py
├── memory.py


"engine.py"

Coordinates the AI conversation and acts as the interface between the application and the AI subsystem.

"api.py"

Handles communication with the selected AI model/API.

"config.py"

Contains AI configuration and system-level instructions.

"memory.py"

Provides persistent conversational context for the prototype.

---

Blockchain Investigation Layer

Decyphra is designed to separate raw blockchain data from the AI reasoning process.

The general flow is:

Raw API Response
       ↓
Extraction
       ↓
Normalization
       ↓
Parsing
       ↓
Formatting
       ↓
Structured Evidence
       ↓
AI

This separation is intentional.

The AI should not have to interpret arbitrary raw API responses when the application can first transform those responses into structured information.

---

Example Investigation

A typical interaction can conceptually look like:

User:
Investigate this wallet.

        ↓

Decyphra retrieves blockchain activity.

        ↓

The data is parsed and normalized.

        ↓

The AI receives the available evidence.

        ↓

Decyphra produces an investigation explaining
the wallet's observed activity.

        ↓

User:
What happened in the most recent transfers?

        ↓

Decyphra continues the investigation.

The goal is not simply to produce another blockchain explorer.

The goal is to create a reasoning interface over blockchain evidence.

---

Current Proof of Concept

TRL 3 — Experimental Proof of Concept

Decyphra is currently an early-stage technical proof of concept.

The prototype demonstrates the feasibility of connecting:

Blockchain data → processing → structured evidence → AI reasoning → natural-language investigation

The current implementation is intended to validate the core technical concept rather than represent a production-ready blockchain intelligence platform.

Demonstrated capabilities

- Wallet-address-based investigation workflow
- Blockchain/API data retrieval
- Transaction and transfer processing
- Data parsing and normalization
- Structured information passed to an AI reasoning layer
- Natural-language analysis
- Conversational follow-up
- Persistent conversational context
- Modular AI architecture

Current limitations

Decyphra is not yet a production-grade blockchain intelligence platform.

Current limitations include:

- Prototype interface
- Limited blockchain/network coverage
- Limited investigation automation
- Limited entity attribution
- No guarantee that every AI interpretation is correct
- Dependence on the blockchain data available to the system
- Limited scalability compared with production blockchain intelligence platforms
- Investigation capabilities are still under active development

These limitations are intentional to the current stage of development.

The purpose of this prototype is to validate the underlying concept and architecture.

---

Screenshots

Wallet Investigation

Example of the current prototype investigating blockchain activity.

---

AI Analysis

Example of the AI reasoning layer interpreting structured blockchain evidence.

---

Prototype Architecture

---

Why Decyphra?

Blockchain explorers are excellent at answering:

"What happened on-chain?"

Decyphra is exploring a different question:

«"What does the activity mean?"»

The long-term vision is to build an investigation interface where users can move from raw blockchain evidence to understandable analysis without needing to manually decode every transaction themselves.

---

Roadmap

Phase 1 — Proof of Concept

- [x] Blockchain data retrieval
- [x] Transaction/transfer processing
- [x] Data normalization
- [x] AI reasoning layer
- [x] Conversational investigation
- [x] Persistent prototype memory

Phase 2 — Investigation Intelligence

- [ ] Multi-chain investigation
- [ ] Improved transaction classification
- [ ] Wallet behavior analysis
- [ ] Entity and address relationship mapping
- [ ] Token-flow analysis
- [ ] Risk indicators
- [ ] Investigation timelines
- [ ] Visual transaction graphs

Phase 3 — Advanced Intelligence

- [ ] Cross-wallet relationship analysis
- [ ] Automated behavioral pattern detection
- [ ] More sophisticated anomaly detection
- [ ] Investigation confidence/evidence indicators
- [ ] Advanced entity clustering
- [ ] Larger-scale blockchain intelligence infrastructure

Phase 4 — Product

- [ ] Web interface
- [ ] Authentication
- [ ] User investigation history
- [ ] Scalable infrastructure
- [ ] Production monitoring
- [ ] Broader blockchain coverage

---

Design Philosophy

Decyphra is being built around several principles:

Evidence over speculation

The system should prioritize observable blockchain evidence over unsupported conclusions.

Explainability

Users should be able to understand why an investigation reaches a particular conclusion.

Human-friendly blockchain intelligence

Complex blockchain data should become easier to understand without hiding the underlying information.

Modular architecture

Blockchain retrieval, parsing, AI reasoning, memory and presentation should remain separable so individual components can evolve independently.

Responsible investigation

An AI-generated interpretation should not automatically be treated as fact.

Attribution, intent and risk require appropriate evidence.

---

Technology

The current prototype is built primarily around:

- Python
- Blockchain APIs
- Structured transaction parsing
- REST APIs
- AI/LLM inference
- Modular Python components
- Conversational memory

The specific infrastructure is expected to evolve as Decyphra progresses beyond the proof-of-concept stage.

---

Project Status

Experimental / Active Development

Decyphra is currently a working proof of concept.

The project is being developed iteratively, with the current focus on validating the core investigation pipeline before expanding into a larger blockchain intelligence platform.

---

Contributing

Decyphra is currently an experimental project.

As the architecture matures, contribution guidelines and development documentation will be expanded.

---


Next Architecture:

WEB APP
                       │
                       ▼
                 PYTHON BACKEND
                       │
                       ▼
               REQUEST HANDLER
                       │
             ┌─────────┴─────────┐
             ▼                   ▼
       New wallet?          Existing state
             │                   │
             ▼                   ▼
      Blockchain APIs       Load investigation
             │                   │
             ▼                   │
       Normalize data            │
             │                   │
             └─────────┬─────────┘
                       ▼
              INVESTIGATION STATE
                       │
                       ▼
                Can answer directly?
                    /        \
                  YES         NO
                   │           │
                   ▼           ▼
                  UI       OpenRouter
                               │
                               ▼
                              LLM
                               │
                         Need more data?
                           /       \
                         NO         YES
                         │           │
                         │       Tool call
                         │           │
                         │       Python
                         │           │
                         │   Blockchain API
                         │           │
                         │       State update
                         │           │
                         └───────┬───┘
                                 ▼
                            Stream result
                                 │
                                 ▼
                                 UI
                                 

Disclaimer

Decyphra is an experimental blockchain analysis tool.

AI-generated interpretations may be incomplete or incorrect and should not be treated as definitive proof of ownership, intent, criminal activity, or identity.

Blockchain analysis should always be evaluated against the underlying on-chain evidence and appropriate external context.

---

Vision

Blockchain gave the world transparent financial infrastructure.

But transparency alone does not guarantee understanding.

Decyphra is exploring what happens when blockchain evidence gets a reasoning layer.

From:

0x...
↓
transactions
↓
transfers
↓
raw blockchain data

to:

"What happened here?"

and ultimately:

"Help me understand this wallet."

That's the problem Decyphra is trying to solve.
