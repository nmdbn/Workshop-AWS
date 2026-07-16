---
title: "FCAJ Community Day"
date : 2026-07-16
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

# Event Report "FCAJ Community Day 23 - 5 - 2026"

## Purpose of the Event
* Share best practices on context engineering when working with AI
* Introduce new agentic AI services/platforms from AWS (Amazon Quick Suite, CloudFront flat-rate pricing, Bedrock AgentCore)
* Present in-depth knowledge on cloud infrastructure: cost optimization, security, reliability, CDN performance
* Analyze the true behavior of LLMs (non-determinism) and how to build reliable AI systems
* Share experiences in building real-world AI products through hackathons and multi-agent applications in the banking sector

## Speakers List
* Tinh Truong - Platform Engineer, GoTymeX
* Pham Ngoc Hai Anh - G-Asia Pacific Vietnam, AWS Community Builder
* Nguyen Tuan Thinh - DevOps Engineer, First Cloud AI Journey (FCAJ)
* Team VIB - LotusHacks 2026
* Duc Dao - Solution Architect, Cloud Kinetics
* Vy Lam - Senior Business Systems Analyst, VPBank

## Key Highlights

**1. Context Is Everything (Tinh Truong)**
Many poor AI responses are due to weak context rather than a bad model. Pointed out 3 common mistakes (overloading information, repeating what AI already knows, not specifying goals/constraints), introduced a 4-step framework for context preparation (Goal – Relevant info – Constraints – Success criteria) and the evolutionary model of Prompt → Context → Memory.

**2. Friendly AI Assistant w/ Amazon Quick (Pham Ngoc Hai Anh)**
Introduced Amazon Quick Suite — a unified agentic AI platform combining company data (40+ connectors), world knowledge, and actions (BI, automation, chat, research) in a governed experience. Demoed a PM assistant use case: automatically creating meeting minutes, emailing stakeholders, and scheduling the next meeting.

**3. From Edge to Origin: CloudFront as Your Foundation (Nguyen Tuan Thinh)**
CloudFront is not just a CDN but a platform to protect and optimize applications. Highlighted the new flat-rate pricing replacing pay-as-you-go to avoid bill spikes. Covered 4 areas: cost optimization (HTTP compression reducing size by 82%), security (DDoS protection at the edge, mTLS, origin cloaking, signed URLs), reliability (origin failover, caching when origin is down), and performance (multi-tier caching, HTTP/3, edge logic processing).

**4. UTMorpho — Building from Idea to Reality (Team VIB)**
The 36-hour journey at the LotusHacks hackathon building UTMorpho — an AI agent that generates UI and allows direct editing on the canvas (WYSIWYG for AI-generated UI), solving the "re-prompting ruins design" issue of current gen-UI tools. Shared challenges (AI generating excess code, token limits, burnout) and lessons: good ideas come from genuine frustration, team chemistry is more important than skills, and AI is a teammate, not just a tool.

**5. Non-Determinism of "Deterministic" LLM Settings (Duc Dao)**
Challenged the popular belief that temperature = 0 ensures 100% reproducible LLM outputs. Research across 5 LLMs and 8 tasks showed accuracy can deviate up to 70% between identical runs due to non-associative floating-point math on GPUs and inference batching mechanisms. Suggested solutions: taking the majority vote across multiple runs, using structured output, and designing systems that accept LLMs as probabilistic rather than deterministic.

**6. Enterprise-Grade Multi-Agent System: Startup Credit Scoring (Vy Lam)**
Traditional bank credit scoring models are unsuitable for startups due to multidimensional and unstructured data. Proposed a "virtual credit committee" architecture consisting of specialized agents (Financial, Market, Team, Risk, Compliance) coordinated by a Manager, producing a credit score, risk rating, and full audit trail. Included 6 enterprise-grade pillars, multi-layered guardrails, and estimated ROI: 95% reduction in processing time, doubled approval rates, and 95% cost savings.

## What We Learned

**AI Design Thinking**
* Context quality matters more than quantity — always prepare goals, constraints, and success criteria before delegating to AI
* AI should be treated as a collaborator that needs correct information, not a "mind-reading machine"
* Great product ideas usually stem from real frustrations in daily workflows, not just chasing trends

**Technical Architecture**
* Multi-agent architecture (specialization, checks & balances, audit trails) outperforms single-agent models for complex, high-risk decisions
* Security and infrastructure require multi-layered design: from perimeter/edge to network, identity, application, and data
* LLMs at temp = 0 can still produce inconsistent results — systems must be designed to accept the probabilistic nature of AI, without assuming absolute determinism

**Deployment Strategy**
* Prioritize high-impact, low-cost "quick wins" (compression, HTTP/3, structured output) before heavy investments
* AI/cloud system deployment should follow a phased roadmap (Foundation → Integration → Pilot → Scale) with clear ROI measurement
* Enterprise-grade is a mindset required from day one (security, compliance, operations), not an afterthought

**Application to Work**
* Apply the context preparation framework when working with AI in daily tasks
* Review production systems using CDNs/LLMs to optimize costs and mitigate risks (bill spikes, non-determinism)
* Consider multi-agent models for multi-dimensional decision-making problems
* Experiment with agentic AI platforms (Amazon Quick Suite, Bedrock AgentCore) to automate repetitive tasks
