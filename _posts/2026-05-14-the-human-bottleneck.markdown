---
title: The Human Bottleneck
date: 2026-05-14 00:00:00 Z
categories:
- Artificial Intelligence
tags:
- Artificial Intelligence
- AI
- Agentic AI
summary: The rapid acceleration of AI-augmented development has fundamentally shifted
  the software delivery bottleneck. As we write code exponentially faster, we are
  generating significantly more code that requires human review. As AI agents rapidly
  convert issues into potential solutions, the traditional pull request queue swells,
  leaving the human reviewer as the primary constraint in the pipeline.
author: dkerr
---

The rapid acceleration of AI-augmented development has fundamentally shifted the software delivery bottleneck. As we write code exponentially faster, we are generating significantly more code that requires human review. As AI agents rapidly convert issues into potential solutions, the traditional pull request queue swells, leaving the human reviewer as the primary constraint in the pipeline.

There is more to gain than ever before from accelerating code delivery, tempting teams to reduce human oversight just to clear the pull request queue. Top-down pressure often drives this push to eliminate the bottleneck, but doing so is fraught with risk from a multitude of standpoints: 

### Security & Compliance
  - **Security Vulnerabilities**: AI can confidently generate pristine-looking code that [harbours subtle flaws](https://www.infosecurity-magazine.com/news/ai-generated-code-vulnerabilities/) (e.g., improper access controls or insecure dependencies).     
  - **Compliance and Licensing**: Models may inadvertently introduce code that violates regulatory frameworks (e.g., GDPR) or [breaches open-source licensing](https://githubcopilotlitigation.com/). 

### System Integrity and Costs
  - **Safety and Reliability**: AI lacks the contextual awareness to evaluate the blast radius of unhandled edge cases, risking [real-world failures](https://ai-analytics.wharton.upenn.edu/wharton-accountable-ai-lab/governing-ai-agents-what-the-amazon-outage-reveals-about-enterprise-risk/) in critical systems. 
  - **Operational Costs**: The costs of utilising the AI models themselves are becoming more notable and harder to predict with leading providers such as [GitHub](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/) and [Claude](https://simonwillison.net/2026/Apr/22/claude-code-confusion/) adjusting pricing plans. Expenses can also escalate if unoptimised logic or inefficient database queries slip through leading to spikes in infrastructure bills.
  - **Testing Blind Spots**: AI can write comprehensive-looking tests that perfectly validate its own flawed or incomplete logic, creating a false sense of security without verifying business requirements. 

### Team Health and Architecture
  - **Long-Term Maintainability**: Unreviewed code frequently introduces architectural drift and inconsistent patterns, [compounding technical debt](https://arxiv.org/html/2603.28592v2) that slows future development. 
  - **Stifling Developer Growth**: Undermining human review eliminates vital touchpoints where junior developers learn the codebase and senior developers provide mentorship.
  - **Erosion of Codebase Comprehension**: If AI writes and humans merely rubber-stamp, teams [lose their mental model](https://addyosmani.com/blog/comprehension-debt/) of the software architecture. This erosion of codebase knowledge limits the engineering team's ability to [effectively prompt and guide AI agents](https://addyosmani.com/blog/cognitive-surrender/) on that same codebase in the longer term.

There are, however, proven ways to relieve this pressure. Strategies like right-sizing risk, balancing short-term velocity with future friction, and automating parts of the review process can help manage the load. 

## Right-Sizing Risk 

In the context of software delivery, "right-sizing" means matching the rigor of your review processes to the actual stakes of the work. Determining the appropriate level of human oversight requires an honest and accurate assessment of your project's risk appetite. While reducing oversight might be perfectly acceptable for a quick proof of concept, a throwaway internal script, or a low-stakes product lacking critical security concerns, applying that same leniency to a more critical system has dangerous consequences. 

The existing 'gold standard' (e.g. [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/)) risk frameworks for determining risk appetite are equally as relevant now as they were before AI-augmented development became mainstream. It's worth engineering teams sitting down with product owners and security teams to explicitly map out and define what 'acceptable risk' looks like for different parts of systems. Once you establish a shared understanding of where defects are a mild annoyance vs catastrophic you can adjust your review bottlenecks accordingly.

The core takeaway, regardless of your risk appetite, is the same: You can delegate the generation of the code to an LLM, but you cannot delegate the accountability. When issues reach a live environment, responsibility rests on the engineering team. By right-sizing your review processes appropriately, you can loosen the leash where the stakes are low, while intentionally preserving enough of a human bottleneck where it is needed most. 

## Balancing short-term velocity against future friction 

When evaluating options to accelerate the review process, you must also consider the trade-offs between immediate velocity and future friction. 

You may successfully reduce the human bottleneck at the review stage, only to encounter the exact same bottleneck further down the software development life cycle. Fast-tracking pull requests can end up translating to bottlenecks at QA or deployment time, ultimately delivering at the same cadence as before. 

Additionally, glossing over reviews to save time shifts the cognitive load from implementation to post-deployment debugging. The cost of fixing defects increases exponentially the later they are caught, with production bugs costing more to resolve than early-phase fixes. 

Under-reviewed code builds up what Addy Osmani refers to as [comprehension debt](https://addyosmani.com/blog/comprehension-debt/) - code that exists but is genuinely not understood by any human. This worsens technical debt and hinders future development as developers build upon systems they are less familiar with. 

Process adjustments, risk right-sizing, and breaking down pull requests form the necessary foundations for managing this new bottleneck. However, it is not ideal to rely upon human discipline alone to enforce these practices. To manage the increasing scale of code to review, teams must equip their reviewers with enhanced capabilities designed specifically for this volume.

## Leveraging Tooling to Reduce Review Load 

Leaning into automated gating and AI-driven pull request tools can significantly reduce the mental burden of human reviewers by pre-filtering noise before the PR is ready to look at.

### AI-Driven PR Reviews 

AI agents can automatically verify codebase rules and review pull requests before a human ever sees the changeset. This needs careful configuration and observation to ensure it doesn't end up causing more work for reviewers who must unpick erroneous suggestions.

Furthermore, teams must guard against the "AI echo chamber": using an LLM to review LLM-generated code can create a dangerous false sense of security where identical models share the same blind spots and confidently validate each other's flawed logic. To mitigate this, treat AI PR tools strictly as pre-review filters for catching boilerplate errors and noise, never as final approvers.

### Next-Generation Static Application Security Testing (SAST) 

Traditional SAST tools are notorious for generating overwhelming amounts of alerts, the vast majority of which are often false positives. In the context of AI-augmented development, dumping this noise into an already swollen pull request queue only exacerbates the human bottleneck.

Next-generation tools address this fatigue by shifting from simple pattern matching to deep contextual understanding. Modern, AI-enhanced static analysis filters out noisy false positives using reachability analysis and contextual filtering, allowing reviewers to focus exclusively on actual, exploitable vulnerabilities.

### Shift-Left Testing and Pre-Commit Automation

By pushing quality checks earlier in the development lifecycle, you can reduce the mental burden on human reviewers. Tools that automatically identify untested code and suggest edge-case tests within the PR can inherently boost your QA pipeline before the code is even merged. 

You can shift the effort even further left by catching boilerplate errors and failing tests before the code is even committed. Leveraging [git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) or [agent hooks](https://code.claude.com/docs/en/agent-sdk/hooks) to run automated linting, builds and tests on the developer's machine pre-commit ensures trivial mistakes are caught instantly, reducing broken code from reaching reviewer.

### Stacked PRs 

Because AI tools inherently drive up pull request sizes, breaking features into [smaller, dependent PRs](https://graphite.com/docs/best-practices-for-reviewing-stacks) prevents massive diffs from overwhelming reviewers. This enforces the author responsibility principle by requiring developers to curate changesets into more digestible chunks rather than offloading the cognitive burden onto the reviewer. 

The traditional overhead associated with managing numerous smaller changes is mitigated by AI tooling itself; by automatically generating PR descriptions and summarising changesets, AI makes it faster and easier to raise code for review, making stacked workflows much more viable for modern development teams.

## Conclusion 

Ultimately, while AI widens the funnel at the top of the development lifecycle, the human bottleneck at the review stage remains a necessary, structural safeguard for long-term project health. 

The goal shouldn't be to eliminate the human from the loop, but to elevate them. By right-sizing your risk, breaking down PRs, and enhancing review tooling, we can effectively manage the human bottleneck and reap the benefits of AI acceleration without compromising code quality.