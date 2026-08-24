# AI Multi-Agent Research & Fact-Checking System

A multi-agent AI research system built with Python and Groq that searches the live web, evaluates source quality, fact-checks claims, and produces evidence-based answers.

## Key Features

* Live web research
* Multi-source evidence collection
* Source credibility evaluation
* Weighted source quality scoring
* Automated fact-checking
* Conflict and uncertainty detection
* Evidence-based answer synthesis
* Multi-model AI workflow
* Secure API key handling with Google Colab Secrets

## System Architecture

```text
User Question
     |
     v
+------------------+
| Research Agent   |
+------------------+
     |
     v
Live Web Search
     |
     v
4 Research Sources
     |
     v
+------------------------+
| Source Evaluator Agent |
+------------------------+
     |
     v
Evidence / Authority / Recency / Relevance
     |
     v
+-----------------------+
| Python Scoring Engine |
+-----------------------+
     |
     v
Source Quality Scores
     |
     v
+------------------+
| Fact Checker     |
+------------------+
     |
     v
Supported / Conflicting / Uncertain Claims
     |
     v
+------------------+
| Synthesis Agent |
+------------------+
     |
     v
Evidence-Based Final Answer
```

## How It Works

1. The **Research Agent** searches the live web for information related to the user's question.
2. The system collects four useful sources instead of relying on a single result.
3. The **Source Evaluator Agent** evaluates each source based on evidence quality, authority, recency, and relevance.
4. A deterministic Python **Scoring Engine** calculates a source quality score.
5. The **Fact Checker Agent** identifies strongly supported, conflicting, and uncertain claims.
6. The **Synthesis Agent** combines the strongest evidence into a final answer without overstating certainty.

## Source Quality Scoring

### Weights

* Evidence & References: **45%**
* Authority: **30%**
* Recency: **20%**
* Relevance: **5%**

### Quality Levels

* **85–100** → Very Strong Source
* **70–84** → Strong Source
* **50–69** → Medium Source
* **Below 50** → Weak Source

## Agents

### Research Agent

Searches the web and collects evidence from multiple sources without assuming the answer beforehand.

### Source Evaluator Agent

Evaluates the quality of each research source.

### Fact Checker Agent

Reviews the collected evidence and identifies:

* Strongly supported claims
* Conflicting claims
* Uncertain claims
* Overall evidence strength

### Synthesis Agent

Combines the research and fact-checking results into a concise evidence-based final answer.

## Python Components

The project also uses deterministic Python logic for tasks that do not require AI reasoning:

* Weighted source scoring
* Source quality classification
* Structured score extraction
* Research workflow orchestration

## Why Use AI + Python?

The AI models handle tasks that require understanding and reasoning, such as evaluating evidence and analyzing claims.

Python handles deterministic calculations such as weighted scoring.

This separation helps make the workflow more predictable and reliable.

## Tech Stack

* Python
* Groq API
* Google Colab
* Browser Search
* OpenAI GPT-OSS 20B
* Qwen 3.6 27B
* Multi-Agent Architecture
* Fact Checking
* Weighted Source Evaluation
* Regular Expressions
* Secure API Key Management

## Example Research Question

```text
Are electric vehicles better for the environment than gasoline cars?
```

The system searches for current evidence, evaluates the quality of the sources, checks conflicting claims, and generates a final evidence-based conclusion.

## How to Run

1. Open `AI_Multi_Agent_Research_Fact_Checking_System.ipynb` in Google Colab.

2. Create a Groq API key.

3. Open **Secrets** in Google Colab.

4. Add the API key using the name:

   `GROQ_API_KEY`

5. Enable notebook access for the secret.

6. Run the notebook cells from top to bottom.

7. Enter or modify the research question.

8. Run the complete research workflow.

> Never hard-code or commit API keys to GitHub.

## What I Learned

This project demonstrates several important AI engineering concepts:

* Multi-agent workflow design
* Live web research with AI
* Source credibility evaluation
* Combining AI reasoning with deterministic Python logic
* Weighted scoring systems
* Fact-checking workflows
* Handling conflicting evidence
* Multi-model workflows
* API rate limits and model fallback strategies

## Project Purpose

This project was built as a hands-on exploration of how multiple AI agents can collaborate with live web search and deterministic scoring to produce more reliable and evidence-based research outputs.
