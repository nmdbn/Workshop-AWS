---
title: "FCAJ Community Day"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# HARVEST REPORT: "FCAJ Community Day 27 - 6 - 2026"

### Event Purpose
* Share practical startup experiences: from idea to execution, and how to find customer champions to bring solutions to production.
* Introduce the architecture and challenges of deploying Voice AI for Vietnamese — a language with diverse regional accents.
* Present operational automation solutions (DevOps Agent) through a real-world case study.
* Introduce the application of Amazon Q in automating the HR recruitment process.
* Explain security configuration when integrating Amazon Q with third-party systems.

### Speakers List
* **Steve Tran** - Cloud Thinker
* **Nghi Danh** - Renova Cloud
* **Trung** - Revve AI
* **Kiet Tran** - AWS Study Group
* **Bao & Nguyen** - Cloud Kinetics
* **Truong & Anh** - Noventiq
* **Toan Nguyen** - AWS Security Builder

---

### Event Highlights

#### 1. Startup Journey Sharing (Steve Tran — Cloud Thinker)
Emphasized the importance of execution rather than just stopping at the idea stage. The speaker shared his experience in finding "customer champions" (such as F88, FPT) as a springboard to move solutions from the PoC (Proof of Concept) stage to Production. The core mindset is to focus on solving actual business problems rather than developing technology for its own sake.

#### 2. Voice AI & Vietnamese Challenges (Nghi Danh — Renova Cloud, Kiet Tran — AWS Study Group, Trung — Revve AI)
Presented the Voice AI system architecture consisting of 3 main components: Speech-to-Text (speech recognition), LLM (logic & language processing), and Text-to-Speech (text to voice). The biggest challenge is handling Vietnamese with diverse regional accents. The optimal solution shared is training the model with about 10–20% regional accents to help the AI understand best while retaining naturalness, rather than trying to fully automate accent translation.

#### 3. DevOps Agent & Operations Automation (Bao & Nguyen — Cloud Kinetics)
Introduced DevOps Agent to automate incident response processes in 4 steps: classification → root cause investigation → solution proposal → system improvement. Real-world results: an online university reduced incident handling time from 2 hours to 28 minutes (77% faster).

#### 4. Amazon Q in Human Resources (HR) (Truong & Anh — Noventiq)
Used Amazon Q to automate resume (CV) screening, candidate competency evaluation, and recruitment process tracking. The benefit is freeing the HR team from repetitive manual tasks to focus on talent retention strategies and optimizing operational costs.

#### 5. Security with Amazon Q (Nghi Danh — Renova Cloud, Toan Nguyen — AWS Security Builder)
Explained how to set up private security for Amazon Q. When connecting Amazon Q with third-party systems (such as Jira, Zalo) via the MCP (Model Context Protocol) gateway, it is crucial to configure a private network to avoid passing through the public internet, ensuring security and confidentiality for enterprise data.

---

### Key Takeaways

#### Startup Mindset
* Execution is more important than just having an idea — act and validate quickly with the market.
* Finding a "customer champion" is the most effective way to take a product from PoC to Production.
* Always start from real business needs, rather than building technology for technology's sake.

#### AI Technology
* 3-tier Voice AI system architecture: Speech-to-Text → LLM → Text-to-Speech.
* For Vietnamese with rich regional accents, training data with a reasonable ratio of regional accents (10–20%) increases accuracy without losing naturalness.
* Standardized incident response automation (classification → root cause → solution → improvement) significantly reduces downtime.

#### AI in Enterprise Operations
* Amazon Q can automate repetitive HR tasks (resume screening, evaluation, tracking).
* When integrating AI with third-party systems via MCP, establish a private network connection to protect sensitive enterprise data.

---

### Lessons Learned
* "Doing" is more important than "thinking" — ideas only have value when they are executed and validated with real customers.
* A pioneering customer (champion) can act as an important lever for a product to transition from PoC to Production.
* For multi-accent/multi-dialect problems, balanced training data is more critical than attempting total automation.
* Operations automation (DevOps Agent) brings clear, measurable performance improvements (77% reduction in incident response time).
* AI is being integrated deeper into business operations, demanding strict security when connecting with external systems.
