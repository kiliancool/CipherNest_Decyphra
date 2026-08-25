Decyphra

AI-Powered Blockchain Wallet Investigation & Intelligence

Turn raw blockchain activity into understandable investigations.

Decyphra is an experimental AI-powered blockchain investigation platform designed to help people understand what is happening inside cryptocurrency wallets.

Instead of requiring users to manually interpret transaction hashes, token transfers, contract interactions, hexadecimal data, and unfamiliar blockchain activity, Decyphra combines blockchain data retrieval, structured evidence processing, and AI reasoning to turn on-chain activity into human-readable investigations.

«Current Stage: TRL 3 — Experimental Proof of Concept»

---

The Problem

Blockchain data is public. Understanding it isn't.

Blockchain explorers provide enormous amounts of information:

- Transactions
- Wallet addresses
- Token transfers
- Contract interactions
- Balances
- Timestamps
- Transaction hashes
- Raw transaction data

But having access to this information does not automatically make it understandable.

A user investigating a wallet may have to move between explorers, token pages, transaction records, contract pages, and external sources while manually trying to connect the evidence.

Questions such as:

«What is this wallet doing?
Where are its assets moving?
What happened recently?
What does this transaction mean?
Is there anything unusual about this activity?»

can require significant blockchain knowledge to answer.

Decyphra explores a simpler approach:

«Make blockchain activity understandable without hiding the underlying evidence.»

---

What Is Decyphra?

Decyphra is being developed as an AI-native blockchain investigation interface.

The long-term goal is not to build another blockchain explorer or simply attach a chatbot to an explorer.

Instead, Decyphra aims to create a system where the AI can work with structured blockchain evidence, determine when additional information is required, retrieve that information through tools, update the investigation state, and explain the resulting findings to the user.

The core interaction is:

INVESTIGATE
     ↓
UNDERSTAND
     ↓
ASK
     ↓
INVESTIGATE DEEPER

A user should be able to start with something as simple as:

Investigate this wallet.

and progressively move toward more detailed questions without having to manually reconstruct the investigation themselves.

---

Core Investigation Concept

The fundamental pipeline is:

Wallet Address
      ↓
Blockchain Data
      ↓
Extraction
      ↓
Normalization
      ↓
Parsing
      ↓
Structured Evidence
      ↓
AI Reasoning
      ↓
Investigation
      ↓
Follow-up Questions
      ↓
Deeper Investigation

The AI is not intended to replace the underlying blockchain evidence.

Its role is to reason over evidence retrieved and processed by the system.

This separation is fundamental to Decyphra's architecture.

---

Evidence-First Intelligence

One of Decyphra's central design principles is:

«Evidence is the foundation of the investigation.»

The system should distinguish between:

What the evidence demonstrates

For example:

- A transfer occurred.
- A wallet interacted with a contract.
- Tokens moved from one address to another.
- A particular transaction occurred at a particular time.

What the system infers

For example:

- The activity may represent a particular behavioral pattern.
- Two addresses may be related.
- A transaction may be consistent with a particular type of activity.

These are not the same thing.

Decyphra is therefore designed around evidence-first reasoning rather than unrestricted AI speculation.

The long-term system should make the relationship between:

Evidence
   ↓
Interpretation
   ↓
Confidence
   ↓
Conclusion

increasingly clear to the user.

---

Current Proof of Concept

TRL 3 — Experimental Technical Proof of Concept

The current version of Decyphra is a working experimental proof of concept.

Its purpose is to validate the fundamental technical idea:

Blockchain Data
      ↓
Processing
      ↓
Structured Evidence
      ↓
AI Reasoning
      ↓
Natural-Language Investigation

The PoC is not intended to represent the final Decyphra product.

It demonstrates that blockchain activity can be retrieved, processed, structured, passed into an AI reasoning layer, and transformed into an interactive investigation experience.

---

What the Current PoC Demonstrates

The prototype demonstrates the core investigation workflow, including:

- Wallet-address-based investigation
- Blockchain/API data retrieval
- Transaction and transfer processing
- Data extraction
- Data normalization
- Transaction parsing
- Structured evidence generation
- AI/LLM reasoning
- Natural-language investigation results
- Conversational follow-up
- Prototype conversational context
- Modular separation between blockchain processing and AI reasoning

The current prototype is intentionally narrower than the planned product.

Its primary purpose is to answer:

«Can an AI reasoning layer make blockchain wallet investigation significantly easier to understand?»

---

Current PoC Architecture

The current architecture separates blockchain data processing from the AI subsystem.

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
                    │ Blockchain / API │
                    │ Data Retrieval   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Extraction /     │
                    │ Parsing          │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Normalization    │
                    │ & Formatting     │
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

The architecture is intentionally modular so that individual components can evolve without requiring the entire system to be rebuilt.

---

AI Subsystem

The AI layer is responsible for interpreting structured investigation data and providing the conversational reasoning interface.

The prototype separates AI responsibilities into modular components.

ai/
├── engine.py
├── api.py
├── config.py
└── memory.py

"engine.py"

Coordinates the AI conversation and acts as the interface between the application and the AI subsystem.

"api.py"

Handles communication with the selected AI inference provider/model.

"config.py"

Contains AI configuration and system-level instructions.

"memory.py"

Provides conversational context for the current prototype.

The AI infrastructure is expected to evolve significantly in the next version as Decyphra moves toward tool-using investigation agents and persistent investigation state.

---

Blockchain Investigation Layer

Decyphra deliberately separates raw blockchain responses from AI reasoning.

The general PoC flow is:

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

This is important because the AI should not have to independently interpret arbitrary raw API responses whenever the application can first transform them into structured information.

The blockchain layer provides the evidence.

The reasoning layer interprets it.

---

Example Investigation

A simplified investigation can look like:

User
 │
 └── "Investigate this wallet."
              │
              ▼
       Retrieve blockchain data
              │
              ▼
       Parse & normalize data
              │
              ▼
       Build structured evidence
              │
              ▼
         AI reasoning
              │
              ▼
      Investigation result
              │
              ▼
User
 │
 └── "What happened in the most recent transfers?"
              │
              ▼
        Continue investigation

The objective is to move away from:

Transaction Hash
        ↓
Explorer
        ↓
Manual interpretation

toward:

Wallet
   ↓
Investigate
   ↓
Understand
   ↓
Ask
   ↓
Investigate deeper

---

Next Planned Version

From Proof of Concept → Investigation Engine

The next planned version moves Decyphra beyond a simple:

Blockchain → AI → Answer

pipeline.

Instead, the system is designed to become an investigation state machine with tool-using AI.

The planned architecture introduces:

- A web application
- A Python backend
- A request handler
- Persistent investigation state
- More structured evidence
- AI tool calling
- On-demand blockchain data retrieval
- Iterative investigation
- Streaming results to the interface

The key architectural change is that the AI should not necessarily receive everything at once.

It should be able to determine:

«Can I answer this from the evidence I already have?»

If not:

«What additional evidence do I need?»

---

Planned Architecture

                         ┌───────────────┐
                         │    WEB APP    │
                         └───────┬───────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │    PYTHON     │
                         │    BACKEND    │
                         └───────┬───────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │    REQUEST    │
                         │    HANDLER    │
                         └───────┬───────┘
                                 │
                    ┌────────────┴────────────┐
                    ▼                         ▼
              New Wallet?              Existing State
                    │                         │
                    ▼                         ▼
           Blockchain APIs          Load Investigation
                    │                         │
                    ▼                         │
             Normalize Data                   │
                    │                         │
                    └────────────┬────────────┘
                                 ▼
                     ┌─────────────────────┐
                     │ INVESTIGATION STATE │
                     └──────────┬──────────┘
                                │
                                ▼
                    ┌─────────────────────┐
                    │ Can Answer Directly? │
                    └──────────┬──────────┘
                               │
                       ┌───────┴───────┐
                       ▼               ▼
                      YES              NO
                       │               │
                       ▼               ▼
                      UI          OpenRouter
                                       │
                                       ▼
                                      LLM
                                       │
                                       ▼
                              Need More Data?
                                /        \
                              NO          YES
                              │             │
                              │             ▼
                              │         Tool Call
                              │             │
                              │          Python
                              │             │
                              │      Blockchain API
                              │             │
                              │       State Update
                              │             │
                              └───────┬─────┘
                                      ▼
                                Stream Result
                                      │
                                      ▼
                                      UI

This architecture is designed around a persistent investigation state rather than treating every user message as an isolated AI request.

---

Tool-Using Investigation

A major planned capability is allowing the AI reasoning layer to request additional information when the existing investigation state is insufficient.

Conceptually:

User Question
      ↓
Investigation State
      ↓
Can current evidence answer it?
      │
   ┌──┴──┐
   │     │
  YES    NO
   │     │
   ▼     ▼
Answer  Request Tool
           │
           ▼
      Python Backend
           │
           ▼
     Blockchain API
           │
           ▼
      New Evidence
           │
           ▼
    Update Investigation
           │
           ▼
        Answer

This enables a more agentic investigation workflow while keeping data retrieval and processing under application control.

The planned AI layer is expected to use OpenRouter as an inference gateway during development, while the underlying model and infrastructure can evolve independently.

---

Investigation State

The next version is intended to maintain a structured representation of an investigation.

Conceptually:

Investigation
│
├── Wallet
├── Networks
├── Transactions
├── Transfers
├── Tokens
├── Contracts
├── Related Addresses
├── Evidence
├── Findings
├── Questions
└── Investigation History

This allows subsequent questions to operate on an existing investigation rather than starting from zero.

For example:

Investigate wallet
        ↓
Find unusual transfer
        ↓
Ask about transfer
        ↓
Retrieve additional data
        ↓
Investigate destination
        ↓
Update state
        ↓
Explain relationship

This is a major step toward Decyphra's long-term vision.

---

Blockchain Data Infrastructure

The project is being designed to work with blockchain data providers rather than relying on a single source indefinitely.

Current development has involved blockchain API infrastructure such as:

- Alchemy
- QuickNode
- BlockOps

The exact provider mix is expected to evolve based on:

- Network coverage
- Reliability
- Data completeness
- API limits
- Cost
- Latency
- Required investigation capabilities

Decyphra's architecture is therefore intended to keep the blockchain data layer replaceable.

---

AI Architecture Philosophy

Decyphra does not treat the LLM as an oracle of truth.

The intended relationship is:

Blockchain / External Evidence
             ↓
       Data Processing
             ↓
      Structured Evidence
             ↓
      Investigation State
             ↓
          AI Reasoning
             ↓
      Human Explanation

Rather than:

Raw Question
     ↓
LLM Guess
     ↓
Answer

This distinction is critical for blockchain investigations because the system may eventually be used to analyze activity involving financial loss, scams, suspicious behavior, or disputed transactions.

AI-generated conclusions should therefore remain distinguishable from directly observable evidence.

---

Planned Investigation Intelligence

As the architecture develops, Decyphra is intended to expand from basic wallet analysis toward broader investigation capabilities.

Planned capabilities include:

Wallet Behavior

- Historical activity analysis
- Transaction patterns
- Asset movement patterns
- Behavioral summaries

Transaction Intelligence

- Improved transaction classification
- Contract interaction interpretation
- Token-flow analysis
- Transaction timelines

Relationship Intelligence

- Address relationship mapping
- Cross-wallet analysis
- Transaction graph exploration
- Entity clustering

Risk & Anomaly Analysis

- Suspicious activity indicators
- Anomaly detection
- Evidence-backed risk signals
- Investigation confidence indicators

These capabilities are planned directions, not claims about the current PoC.

---

Current Limitations

Decyphra is not yet a production-grade blockchain intelligence platform.

Current limitations include:

- Early-stage prototype architecture
- Limited blockchain/network coverage
- Limited investigation automation
- Limited entity attribution
- Limited relationship analysis
- Limited behavioral intelligence
- Dependence on available blockchain API data
- AI interpretation can be incomplete or incorrect
- No guarantee that an inferred relationship represents actual ownership or control
- No guarantee that observed activity establishes intent
- Scalability and reliability are not yet production-level

These limitations are expected at the current TRL 3 stage.

The purpose of the PoC is to validate the underlying technical direction before investing in the larger production architecture.

---

Roadmap

Phase 1 — Technical Proof of Concept

Status: Current

- [x] Wallet-address investigation workflow
- [x] Blockchain API integration
- [x] Transaction/transfer processing
- [x] Data extraction
- [x] Data normalization
- [x] Structured evidence generation
- [x] AI reasoning layer
- [x] Natural-language investigation
- [x] Conversational follow-up
- [x] Prototype conversational context

---

Phase 2 — Investigation Engine

Status: Planned

- [ ] Web application
- [ ] Python backend
- [ ] Request handling layer
- [ ] Persistent investigation state
- [ ] Investigation history
- [ ] Structured evidence model
- [ ] AI tool calling
- [ ] On-demand blockchain retrieval
- [ ] Streaming investigation results
- [ ] Improved transaction classification

---

Phase 3 — Investigation Intelligence

Status: Planned

- [ ] Multi-chain investigation
- [ ] Wallet behavior analysis
- [ ] Token-flow analysis
- [ ] Address relationship mapping
- [ ] Cross-wallet investigation
- [ ] Investigation timelines
- [ ] Risk indicators
- [ ] Anomaly detection
- [ ] Visual transaction graphs
- [ ] Evidence/confidence indicators

---

Phase 4 — Intelligence Platform

Status: Long-term

- [ ] Broader blockchain coverage
- [ ] Advanced entity clustering
- [ ] Large-scale investigation infrastructure
- [ ] Production-grade reliability
- [ ] Authentication and user accounts
- [ ] Investigation history
- [ ] Scalable cloud infrastructure
- [ ] Monitoring and observability
- [ ] API / developer access
- [ ] B2B investigation capabilities

---

Design Principles

1. Evidence Over Speculation

Observable evidence should take precedence over unsupported conclusions.

2. Explainability

Users should understand how an investigation reaches a finding.

3. Human-Friendly Blockchain Intelligence

Complex blockchain information should become easier to understand without hiding the underlying evidence.

4. Modular Architecture

Blockchain retrieval, parsing, investigation state, AI reasoning, memory, and presentation should remain separable.

5. AI as a Reasoning Layer

The LLM should interpret and reason over evidence rather than become the source of that evidence.

6. Progressive Investigation

Users should be able to start with a simple question and progressively investigate deeper.

7. Responsible Interpretation

Wallet ownership, identity, intent, criminality, and risk should not be asserted solely because an AI model produced a conclusion.

---

Technology

Current PoC

The current proof of concept is primarily built around:
Python
Blockchain APIs
REST APIs
Transaction parsing and normalization
Structured data processing
AI/LLM inference
Modular Python components
Conversational context


 Planned Version
The next architecture is expected to introduce:
Web application
Python backend
Investigation state
Tool-using AI
OpenRouter-based model access during development
Blockchain API tools
Streaming responses
Persistent investigation history
More structured evidence and investigation models
The exact infrastructure and model selection may evolve as the project moves beyond the PoC.


Screenshots
Current Prototype
Check /assets



Why Decyphra?
Blockchain explorers are excellent at answering:
"What happened on-chain?"
Decyphra is exploring a different question:
"What does the activity mean?"

While Blockchain investigation platfroms like Chainanalysis, TRM labs, Nansen, are institutionally oriented
The difference is not simply presentation.
It is the transition from searching blockchain data to the ability for all and not just institutions to conduct an investigation over blockchain evidence.

Project Status
Experimental — Active Development
Decyphra is currently a TRL 3 technical proof of concept.
The project has validated the core concept of connecting blockchain data processing with an AI reasoning layer.
The next major step is to evolve the prototype into a web-based investigation engine capable of maintaining investigation state, answering questions from existing evidence, and retrieving additional blockchain data through controlled tools when necessary.

Disclaimer
Decyphra is an experimental blockchain analysis and investigation project.
AI-generated interpretations may be incomplete, uncertain, or incorrect and should not be treated as definitive proof of:
Identity
Ownership
Intent
Criminal activity
Fraud
Malicious behavior
Control of an address
Blockchain analysis should always be evaluated against the underlying on-chain evidence and, where appropriate, additional external context.
Decyphra is intended to assist investigation and understanding, not replace human judgment or establish definitive conclusions on its own.


Vision
Blockchain gave the world transparent financial infrastructure.
But transparency alone does not guarantee understanding.
Today, a user may see:
0x...
   ↓
Transactions
   ↓
Transfers
   ↓
Contract Calls
   ↓
Raw Blockchain Data
Decyphra's vision is to transform that experience into:
Wallet
   ↓
INVESTIGATE
   ↓
UNDERSTAND
   ↓
ASK
   ↓
INVESTIGATE DEEPER

Ultimately, the goal is simple:
Help people understand what is happening inside a blockchain wallet without requiring them to become blockchain experts first.
Decyphra is exploring what happens when transparent blockchain data gets an intelligent, evidence-first reasoning layer.

Repository Status
Current: TRL 3 Experimental Proof of Concept
Next: Web-Based AI Investigation Engine
Long-Term: AI-Native Blockchain Intelligence Platform
