# Hey, I'm Aman Rajput

Full-Stack AI Engineer focused on building production-grade AI systems — multi-agent pipelines, RAG architectures, and local-first LLM applications.

I build systems that are:
- **Fast** (async pipelines, low-latency inference)
- **Reliable** (retry logic, backpressure, fault tolerance)
- **Scalable** (distributed systems, queues, observability)
  
Comfortable across the full stack.

---

## Technical Skills

**Languages:** Java (Primary), JavaScript, TypeScript, Python, C++, SQL  

**Backend & Systems:** REST APIs, Multithreading, Async Job Queues, Distributed Systems, PostgreSQL, MongoDB, Redis, Prisma  

**Frontend:** React, Next.js, TypeScript, Component-Driven Architecture, WebRTC, WebGPU, PWA  

**AI / Agentic Systems:** LLM APIs, RAG Pipelines, Multi-Agent Orchestration, Embeddings, Tool Use, ReAct Loops, FAISS, Prompt Engineering  

**Tools & Platforms:** Git, Docker (Basics), Linux, Node.js, Railway, Vercel, Langfuse, Supabase  

**Engineering Practices:** OOP, Clean Code, Observability, Performance Optimization, Scalability, First-Principles Design

---

##  Projects

### [AgenticArXiv](https://github.com/amanrajput-ar15/AgenticArXiv-mvp) — Multi-Agent Research System
`FastAPI` `Gemini 2.5 Flash` `FAISS` `MongoDB` `Redis` `Langfuse`

An async research pipeline that ingests ArXiv PDFs and runs a 5-agent RAG system to produce structured research reports.

- **Async job queue** (FastAPI + Redis BRPOP + background worker) cuts API response time from >60s to <100ms and enables horizontal scale under concurrent load
- **5 specialized agents** (Literature, Methods, Results, Critique, Synthesis) over a FAISS 768-dim vector index — Gemini 2.5 Flash vision parses multi-column PDFs, gemini-embedding-001 handles semantic retrieval — at ~$0.002/query
- **Production resilience**: exponential backoff with jitter for Gemini 429/503 errors, FAISS dimension guard against silent index corruption on model migration, cross-platform file locking (fcntl/portalocker) for concurrent writes
- **Observability**: Langfuse distributed tracing with per-agent latency spans; progressive MongoDB writes let the frontend render partial results as each agent completes

---

### [VoidChats](https://github.com/amanrajput-ar15/voidchats) — In-Browser AI Chat App
`Next.js` `WebGPU` `WebLLM` `Transformers.js` `AES-GCM` `PWA`

A fully offline AI chat app — no server, no API costs. A 3B-parameter quantized LLM (Qwen 2.5) runs entirely in the browser.

- Achieves **~2 tok/s on integrated GPU**, ~40 tok/s on dedicated NVIDIA hardware via WebGPU
- **Semantic context eviction** using in-browser embeddings (all-MiniLM-L6-v2, 25 MB) + cosine similarity to retain relevant history within a 2,048-token window — outperforms FIFO truncation on long sessions
- **Zero-knowledge encryption**: Web Crypto API (AES-GCM + PBKDF2, 100k iterations) secures all chat data in IndexedDB; no plaintext ever leaves the device; ~30 kB lighter than CryptoJS
- Resolved 7 production-grade failure modes: WebGPU singleton crash from React Strict Mode double-invocation, WASM GC pointer bug in Transformers.js, Service Worker interference with HMR

---

### [Multithreaded TCP Web Server](https://github.com/amanrajput-ar15/Multithreaded-Web-server-JAVA) — Systems Deep Dive
`Java` `TCP Sockets` `ExecutorService` `java.util.concurrent`

Built and benchmarked three concurrency architectures from scratch in raw Java TCP.

- Compared **single-threaded, thread-per-connection, and thread-pool** models under 100-client concurrent load — measured throughput, latency, and resource consumption
- Fixed thread-pool (ExecutorService, 10 workers, LinkedBlockingQueue) maintains **bounded memory** under load vs. thread-per-connection which exhausts OS limits (~1,000–10,000 threads) at scale
- **CallerRunsPolicy backpressure** + bounded queue (ArrayBlockingQueue, capacity 100) gracefully throttles connections rather than dropping them — same pattern used in Netty, Tomcat, and production HTTP servers

---

##  Tech Stack

| Area | Tools |
|---|---|
| **Languages** | Java (Primary), JavaScript, TypeScript, Python, C++, SQL |
| **Backend** | REST APIs, Multithreading, Async Job Queues, Distributed Systems |
| **Databases** | PostgreSQL, MongoDB, Redis, Prisma |
| **Frontend** | React, Next.js, TypeScript, WebRTC, WebGPU, PWA |
| **AI / Agentic** | LLM APIs, RAG Pipelines, Multi-Agent Orchestration, FAISS, ReAct Loops |
| **Tools** | Git, Docker, Linux, Node.js, Railway, Vercel, Langfuse, Supabase |

---

##  Achievements

- **AIR 2321 – JEE Advanced 2023** — top 0.3% nationally among ~1 million candidates
- **LeetCode Contest Rating 1600+** — consistent performance in timed contests; strong in DSA, graphs, and DP (Java)

---

##  Get in touch

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)]([https://linkedin.com](https://www.linkedin.com/in/aman-rajput-ar113114/))
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:iamanrajput00@gmail.com)
