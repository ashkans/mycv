# Learning Opportunities: Model Evaluations for ML

> Context: Gaps identified while preparing for Canva Senior MLE - Visual Suite role.
> Goal: Sharpen edges on model evaluation — already a strong area, just need to bridge to industry/product context.

---

## Your Existing Strengths (no learning needed — just frame well)

- Rigorous offline evaluation with baseline comparisons (LSTM: 20% over baseline)
- Evaluation at scale (Random Forest: 70% accuracy on 1M+ data points)
- Temporal evaluation across forecast horizons (Fire Danger: 30% boost up to 3 months ahead)
- Cross-validation against independent data sources (Ensemble Kalman Filter + GRACE satellite)
- Ongoing operational model monitoring (AWRA-L v7: thousands of daily users)
- Peer-reviewed evaluation methodology (20+ publications, NeurIPS reviewer)

---

## 1. LLM / Generative Model Evaluation (Priority: HIGH)

**Why learn this:**
- Canva's Visual Suite (Docs, Presentations, Whiteboards) almost certainly uses generative AI features
- As an ML enablement engineer, you'll help product teams evaluate LLM-based features
- This is the fastest-growing area of ML evaluation and a hot interview topic

**What to learn:**
- **Traditional NLG metrics**: BLEU, ROUGE, METEOR — what they measure and their limitations
- **LLM-as-judge**: using a stronger LLM to evaluate outputs of another LLM (e.g., GPT-4 scoring GPT-3.5 outputs)
- **Human preference evaluation**: Elo ratings, pairwise comparisons, annotation guidelines
- **Evaluation dimensions for generative AI**: fluency, factuality, relevance, safety, helpfulness
- **Red-teaming**: adversarial testing for harmful, biased, or incorrect outputs
- **Eval frameworks/tools**: Braintrust, Humanloop, OpenAI Evals, LangSmith, custom eval harnesses
- **Regression testing for LLMs**: golden datasets, snapshot testing, detecting quality degradation across model versions

**Learning plan (~1-1.5 hours):**
1. [ ] Watch a video on "LLM Evaluation" (search "how to evaluate LLM outputs" or "LLM evaluation framework")
2. [ ] Read the OpenAI Evals or Braintrust documentation overview (~15 min)
3. [ ] Understand the LLM-as-judge pattern: prompt design, scoring rubrics, agreement metrics
4. [ ] Be able to explain: "How would you evaluate a text generation feature?", "What are the limitations of automated metrics for LLMs?", "How do you catch regressions in generative model quality?"

**How to talk about it in interviews:**
- "For generative AI features, I'd set up a multi-layered evaluation approach: automated metrics for fast iteration, LLM-as-judge for scalable qualitative assessment, and human evaluation for final validation. I'd also build golden datasets for regression testing so teams can confidently ship model updates."

---

## 2. A/B Testing & Online Experimentation (Priority: MEDIUM)

**Why learn this:**
- At Canva, model evaluation doesn't stop at offline metrics — real value is measured through user impact
- As an enablement engineer, you'd help teams design and interpret experiments
- Bridges your strong offline evaluation skills to the product/online world

**What to learn:**
- **Core concepts**: control vs treatment, statistical significance, p-values, confidence intervals
- **Guardrail metrics**: metrics that must not degrade (latency, crash rate, revenue) even if the target metric improves
- **Sample size & duration**: how long to run an experiment, power analysis basics
- **Common pitfalls**: peeking, novelty effects, Simpson's paradox, interference between experiments
- **How A/B testing fits ML deployment**: canary rollouts → shadow mode → A/B test → full rollout
- **Tools**: Statsig, LaunchDarkly, Optimizely, or custom internal platforms

**Learning plan (~30-60 min):**
1. [ ] Watch a short video on "A/B testing for ML" or "online experimentation basics"
2. [ ] Read one blog post on A/B testing pitfalls (Evan Miller's "How Not To Run an A/B Test" is a classic)
3. [ ] Understand the ML deployment progression: offline eval → shadow mode → canary → A/B test → full rollout
4. [ ] Be able to explain: "How would you decide if a new model is better than the current one in production?", "What guardrail metrics would you track?"

**How to talk about it in interviews:**
- "Offline evaluation tells you if a model *can* work; online experimentation tells you if it *does* work for users. I'd advocate for a staged rollout: validate offline metrics first, then shadow-test against production, then run a controlled A/B test with clear success criteria and guardrail metrics before full deployment."

**Your existing experience that connects:**
- Operational model ownership at BoM (AWRA-L v7 serving thousands daily) — you understand what it means to have a model in production that users depend on
- Baseline comparisons across all your models — the same principle applies to A/B tests (old model = control, new model = treatment)

---

## Summary

| Topic | Priority | Time Investment | Type |
|---|---|---|---|
| LLM / Generative Model Evaluation | HIGH | 1-1.5 hours | Conceptual (video + reading) |
| A/B Testing & Online Experimentation | MEDIUM | 30-60 min | Conceptual (video + blog post) |

**Total estimated time: 1.5-2.5 hours**

**Note:** Model evaluation is already one of your strongest areas. These additions just bridge the gap from scientific/research evaluation to product/industry evaluation at a company like Canva.
