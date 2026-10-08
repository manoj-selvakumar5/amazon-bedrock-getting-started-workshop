# Amazon Bedrock Getting Started Workshop (AIM317)

Hands-on workshop that takes you from your first [Amazon Bedrock](https://aws.amazon.com/bedrock/)
API call to a working application in one session. You choose a model, ground it with a Managed
Knowledge Base, apply Guardrails, pick a service tier, then deploy and monitor what you built.

- Duration: x hours ( will need to confirm)
- Level: 200 (you know AWS basics and are new to Amazon Bedrock)
- Format: Jupyter notebooks
- Region: `us-east-1` or `us-west-2`

## What you build

An employee travel assistant for AnyCompany, a fictional company. It starts as a plain chat and
gains one capability per module, so you finish with one deployed, monitored application rather
than a set of separate demos. It does two jobs:

- **Travel chat**: answers employees' travel questions from AnyCompany's travel policy, with
  citations.
- **Expense checks**: checks expense reports against the policy and returns APPROVED or FLAGGED,
  with a reason.

| Model | Used for |
|---|---|
| Claude Sonnet 5 (Anthropic) | Travel chat |
| gpt-oss-120b (OpenAI, open-weight) | Expense checks |
| GPT-5.6 Luna (OpenAI) | The OpenAI Responses API example in Module 1 |

## Modules

Each module adds a capability and leads into the next one.

| # | Notebook | What the assistant gains | Status |
|---|---|---|---|
| 0 | [Setup](notebooks/00_setup.ipynb) | Python packages installed, invocation logging on | Ready |
| 1 | [First call](notebooks/01_first_call.ipynb) | A travel chat assistant built on the Converse API | Ready |
| 2 | [Choosing a model](notebooks/02_choosing_a_model.ipynb) | The right model for each task, chosen by measuring quality, accuracy, latency and cost | Ready |
| 3 | [Grounding with a Managed Knowledge Base](notebooks/03_knowledge_base.ipynb) | Chat answers and expense checks grounded in the travel policy | Ready |
| 4 | [Guardrails](notebooks/04_guardrails.ipynb) | Personal data redacted, out-of-policy requests blocked, unsupported answers flagged | Draft |
| 5 | [Service tiers](notebooks/05_service_tiers.ipynb) | Faster expense checks on the Priority tier when an employee is waiting | Draft |
| 6 | [Deploy and monitor](notebooks/06_deploy_and_monitor.ipynb) | Deployed on AWS Lambda, with logs, metrics and cost attribution | Draft |
| - | [Cleanup](notebooks/99_cleanup.ipynb) | Deletes the resources created in the workshop | Draft |
| - | [Stretch: AgentCore](notebooks/stretch_agentcore.ipynb) | The assistant as an agent on Amazon Bedrock AgentCore Runtime | Draft |

## Getting started

At an AWS event, your account and environment are set up for you. Open
`notebooks/00_setup.ipynb` in Jupyter and run it: it installs the packages in `requirements.txt`
and turns on model invocation logging. Then work through the notebooks in order.

## Repository layout

| Path | Contents |
|---|---|
| `notebooks/` | Workshop notebooks, run in order |
| `data/` | AnyCompany travel policy documents and sample expense reports |
| `app/` | The deployable assistant (Module 6) |
| `infra/` | CloudFormation for resources set up in event accounts |
| `requirements.txt` | Python packages, installed by Module 0 |
