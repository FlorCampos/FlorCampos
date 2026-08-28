## Hi there 👋

<h1 align="center">Flor Campos Flores</h1>
<p align="center">
  <b>GenAI &amp; Agentic Engineer</b> · Montréal, Canada<br>
  I build LLM systems in production and I test them.
</p>
<p align="center">
  <a href="https://www.linkedin.com/in/florcampos/">LinkedIn</a> ·
  <a href="{{portfolio-url}}">My_Website_In_Process</a>
</p>
---
 
I’m Flor Campos Flores. I work as a GenAI Engineer and AI Agentic Engineer, 
helping companies and people take AI systems from concept to production with quality, 
scalable architecture, and less time and cost. Over 8 years in QA automation engineering
is what taught me to build them that way. That background is the
point: most GenAI projects ship without an eval suite, without cost visibility, and
without anyone asking how they fail. Mine ship with all three.
 
**Focus:** RAG architecture · agentic systems &amp; tool calling · LLM evaluation and
red-teaming · GenAIOps (cost tracking, caching, guardrails, observability)
 
---
 
### Selected work
 
#### [Nesta — RAG career companion, deployed in production](https://github.com/FlorCampos/nesta-gemini)
Built for Her Career Conference 2026 (District3, Montréal). FastAPI + Claude for
generation, Gemini for embeddings, Supabase/pgvector for retrieval, Redis for caching,
Firebase for the frontend, containerized for Cloud Run.
 
What's actually inside the pipeline, and each piece has a test behind it:
intent classifier → query router → semantic chunker → retriever → reranker →
PII anonymizer → guardrails and hard limits → response modes → cache layer.
 
Engineering details worth opening the repo for:
- **Per-call cost accounting.** Real input/output token counts priced at call time,
  plus embedding cost, plus the savings attributed to cache hits.
- **Error responses are never cached.** Caching a transient failure means serving that
  failure for the length of its TTL — a real incident, fixed by pattern-matching failure
  responses before they ever reach Redis.
- **Knowledge base built from primary sources.** Conference sessions, speakers and
  workshops, plus a curated corpus of public labour-market and AI research
  (WEF Future of Jobs 2025, WEF Putting Skills First, McKinsey superagency reports,
  Quebec employment and language studies) processed from PDF into retrievable chunks.
- **16 automated test files** across unit, integration and end-to-end — including
  stress and routing tests, not just happy paths.
`Python` `FastAPI` `Claude` `Gemini` `Supabase/pgvector` `Redis` `Docker` `Cloud Run` `Firebase`
 
#### nesta-qa — evaluation &amp; red-teaming harness for LLM systems
The testing layer behind Aati. DeepEval for faithfulness, contextual precision/recall,
guardrail and PII checks; k6 with Grafana for load testing streaming endpoints; each tool
isolated with Docker Compose. Load testing is how the caching bug above was found before
users ever saw it.
`DeepEval` `Ragas` `Promptfoo` `Garak` `PyRIT` `k6` `Grafana`
 
#### [Clarity — AI agent that turns raw requirements into QA artifacts](https://github.com/FlorCampos/clarity)
Claude + ChromaDB + Whisper, with Azure DevOps integration. Built for software teams that
lose days translating discovery calls into test coverage.
`Python` `Claude` `ChromaDB` `Whisper` `Streamlit`
 
---
 
### How I work
 
- **Evaluation before features.** If a change can't be measured against a test suite, it
  isn't done. Nine unit test files exist for a reason: chunking, routing, reranking,
  anonymization and guardrails each fail in their own way.
- **Cost is a design constraint.** Token accounting and caching belong in the first
  version, not in the optimization pass after the bill arrives.
- **Secrets hygiene.** After a credential leak in a collaborative repo, I rewrote the git
  history with `git-filter-repo`, rotated every key, and wrote the post-mortem. Secret
  scanning now runs in pre-commit on my projects.
- **Adversarial by default.** Eight years of QA means I look for how a system breaks
  before I write the demo.
### Stack
 
| | |
|---|---|
| **AI / GenAI** | Claude API · Gemini · OpenAI · LangChain · RAG pipelines · MCP · tool calling · prompt engineering · guardrails |
| **Backend** | Python · FastAPI · Pydantic · SSE streaming · REST · Redis |
| **Data & cloud** | Supabase / pgvector · ChromaDB · GCP (Cloud Run, Vertex AI, Firebase) · Docker · CI/CD |
| **Evaluation & QA** | DeepEval · Ragas · Promptfoo · Garak · PyRIT · k6 · Grafana · pytest · LLM-as-judge |
 
### Background
 
Senior QA Automation Engineer → GenAI Engineer. B.Sc. Computer Science ·
Software Engineering with Generative AI specialization, Concordia University (in progress) ·
MIT Professional Certificate in Cybersecurity. EN / ES / FR.
 
<sub>Open to remote GenAI and agentic engineering work.</sub>
 
