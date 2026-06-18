---
title: If AI Writes the Code, Who Builds the Next Open Source Project?
date: 2026-03-15 20:12:00 Z
categories:
- Artificial Intelligence
tags:
- Artificial Intelligence
summary: AI was trained on open source, but its rapid progress is now raising difficult
  legal, technical, and cultural questions for the ecosystem that enabled it. From
  copyright and “fair use” debates to AI-generated code, cloned frameworks, and autonomous
  coding agents, this post explores how AI may reshape the future motivations and
  sustainability of open source.
author: ceberhardt
image: "/uploads/open-source-logos.png"
---

Open source has long been driven by human frustration, curiosity and craftsmanship, creating better tools because existing ones didn’t quite feel right. But as AI agents increasingly write code for us, that dynamic may be changing.

In this post I look at how AIs impact on open source; from the legal debates over training data, the uncertain copyright status of AI-generated code, the possibility of AI-driven project cloning, and the growing strain on maintainers. Finally, I consider what happens to open source when the people who create it start to feel less of the friction that once inspired it.

## Is AI training on open source ‘fair use’? Or a copyright violation?

When LLMs burst into our personal and professional lives in 2021-22, with the launch of ChatGPT and GitHub Copilot, they were met with a mixture of wonder and concern. Their amazing capability was only made possible by a long process of deep learning on a vast corpus of text and code.

Copilot was trained on public GitHub repositories, which contain a wide range of licences ranging from the more permissive (e.g. MIT, Apache 2.0) to more restrictive (e.g. GPL). The model labs that scooped all of this data up argued that this constitutes ‘fair use’, a transformative work, rather than a direct reproduction of copyright materials. However, many open source developers viewed this differently, especially when Copilot would often [emit large sections of copyright code](https://www.devclass.com/ai-ml/2022/10/17/github-copilot-under-fire-as-dev-claims-it-emits-large-chunks-of-my-copyrighted-code/1621842) – including the copyright notice itself!

Some maintainers took action (beyond complaining on Reddit!); the Free Software Foundation funded a call for white papers to analyse the issue, but there has been little progress on this since. There is also an ongoing class-action lawsuit, [Doe v. GitHub, Inc.](https://www.bakerlaw.com/the-copilot-litigation/) which contains various claims including open source licence violation and removal of copyright information. However, [many of these claims have been dismissed](https://www.pearlcohen.com/copyright-claims-against-github-microsoft-and-openai-largely-dismissed/?utm_source=chatgpt.com).

In May last year the US copyright office published a [pre-publication draft on Generative AI](https://www.copyright.gov/ai/Copyright-and-Artificial-Intelligence-Part-3-Generative-AI-Training-Report-Pre-Publication-Version.pdf?stream=top). They made it clear that training cannot automatically be considered fair use, and specifically called out the need for lawful access (i.e. don’t train on data that has been acquired illegally). However, beyond that, it basically said “it is complicated”, leaving it to courts to apply judgement on a case-by-case basis.

I don’t think any future court rulings or changes in law are going to have a meaningful impact here. Large-scale training on ‘public’ datasets, which in the case of open source is any code found on the internet (regardless of licence) looks like it is here to stay. Unfortunately, the only way to prevent your code from being used for AI training is to not make it public.

## Can you copyright AI-authored code?

Fast forward to 2026, we’re now in an era where significant amounts of code is AI-authored, which leads to a completely different legal question; can AI-generated code be copyrighted?

In the U.S. copyright law protects “original works of authorship.” where authorship is considered to be the work of a human. The courts have recently [declined to consider whether AI-generated art can be copyright,](https://www.cnbc.com/2026/03/02/us-supreme-court-declines-to-hear-dispute-over-copyrights-for-ai-generated-material.html) doubling-down on the need for direct human authorship. And [recent guidance states](https://www.copyright.gov/ai/):

> “Material generated wholly by artificial intelligence is not eligible for copyright protection.”

This does of course leave a lot to interpretation. In the field of software engineering, what does “generated wholly by artificial intelligence” mean? If you follow a specification driven development workflow, where you don’t touch any of the generated code, presumably you cannot copyright the code. But what if you review and edit the output? Can the code them be copyright?

Unfortunately, without being able to claim copyright, you cannot employ any of the standard open source licences to your work.

I would seem that the copyright system is struggling to keep up with AI; and open source which, is deeply dependent on this legal system, will probably suffer.

## AI cloning of open source code – a moral dilemma

Recently we have seen a significant improvement in the ability of LLMs to write code. This was reflected in the benchmarks, for example state-of-the-art performance on [SWE-Bench](https://www.swebench.com/SWE-bench/) leapt from about 10% at the beginning of 2024, to around 80% at the end of 2025. As well as raw model performance, the concept of agentic loops – where a model iterates on a problem, supported through the use of tools – became mainstream in 2025, allowing agents to take on much more complex problems.

With agentic loops, the feedback mechanism has a significant impact on the model's ability to be able to autonomously pursue a goal. Comprehensive test suites, or a reference implementation, are fantastic feedback loops, that have allowed agents to do some truly impressive things. For example:

* Last month, the anthropic team [built a C compiler](https://www.anthropic.com/engineering/building-c-compiler), achieving a 99% benchmark score, in just a few weeks, relying heavily on existing test suites to guide the agent.


* A few weeks ago, the [Cloudflare team created a clone of Next.js](https://blog.cloudflare.com/vinext/) that more readily runs on their cloud platform, again, using the existing test suite to steer the agent.


* And last week, the chardet project used an AI agent to re-implement one of their dependencies, in order to free them of the GPL licence restrictions. The author of this open source, LGPL licenced dependency [was not happy](https://github.com/chardet/chardet/issues/327).

Whether you can re-write software is a familiar legal issue, with much of the debate around the chardet re-write focussing on whether this can be considered a “clean room” implementation. This term originated in the 1980s, describing a legally robust technique for replicating software by having one team document an existing system, then an entirely separate team re-implement based on the specification. Can an AI re-write be considered “clean room” given that the original sourcecode is almost certainly in its training dataset?

Unfortunately, as with the fair use and copyright issues described above, it is going to take a long time for the legal system to catch up with the capability of AI agents. The concepts of “fair use” and “clean room” were created in a time when this type of AI capability was entirely inconceivable.

As well as a legal issue, this is also a moral issue. Is it fair to copy someone else’s work? How do maintainers feel about this? Especially given that the better the quality of your tests and documentation, the more exposed you are to being cloned.

## AI contributions and bots

A growing number of open source contributors are now using AI tooling to assist them, which is of course entirely expected and not necessarily a bad thing. However, while AI can be used to create quality contributions, by taking care and reviewing the output. It can also be used to very rapidly create poor quality contributions, or ‘AI slop’.

GitHub have acknowledged that t[here has been an increase in low-quality contributions](https://github.com/orgs/community/discussions/185387) and are looking for community feedback on various ways to tackle it.

Maintainers have mixed views on accepting AI-authored, or AI-assisted contributions. There have been a few high-profile cases of [open source projects outright banning AI contributions](https://etn.se/index.php/nyheter/72808-curl-removes-bug-bounties.html), however, a [recent review of 112 open source projects](https://theconsensus.dev/p/2026/03/02/source-available-projects-and-their-ai-contribution-policies.html) show that most are quite welcoming. Only four of the projects ban AI contributions, and 71 have merged commits that mention being written with AI assistance. Although if the slop problem increases, I wonder whether more projects will ban the use of AI? Also, a recent study claims that while 95% of contributions were fully or partially AI-generated, only 29% of contributors explicitly disclose their use of AI.

So far, most of these AI-assisted contributions have been from human beings, and even in the case where they are wholly AI-generated, a human being has been ‘in the loop’ to a certain extent. This is changing; with the sudden rise in popularity of OpenClaw, we are seeing many people experiment with fully autonomous agents, and it is no great surprise that some of these ‘claws’ are now being let loose on GitHub. I’ve already [crossed paths with a bot](https://github.com/botbotfromuk) that commented on an issue I was participating in, and its comment added little value.

If you’ve read Nadia Eghbal book [“Working In Public”,](https://www.goodreads.com/book/show/54140556-working-in-public) which explores the open source community, you’ll know that the scarcest resource is a maintainer’s attention, and it is a resource that doesn’t scale terribly well. Poor quality contributions steal attention. We’ve seen the damaging effects of this in the past, with some calling Hacktoberfest (which encourages people to contribute to open source to win T-Shirts) a [distributed denial of service attack](https://domenic.me/hacktoberfest/).

I fear there will be a growing amount of noise due to fully autonomous agents ‘helpfully’ working in open source, creating further stress on maintainers.

## Do AI agents need open source?

So far, we’ve seen that AI models were trained on open source, via a questionable interpretation of far use, that open source projects can now be cloned with relative ease, and that there will likely be a significant rise on automated slop contributions. The impact of AI on open source doesn’t look all that great. However, I think there will likely be a more significant long-term impact caused by the widespread adoption of AI agents for coding.

Where does open source come from in the first place?

Evan You, the creator of Vue.js, wanted something that fit the way he thinks about building user interfaces. Rich Harris, of Svelte fame, wanted a framework that disappeared. Ryan Dahl, of Node fame, created Deno, to address the mistakes he’d made with Node. These are just a few examples, there are a great many more, but an underlying theme here is that maintainers create projects to address friction they have experienced themselves. They had an unpleasant experience with a framework, platform or library, and decided to create something with a better user experience.

As we increasingly lean on agentic AI, we no longer directly feel the pain of a poorly designed library. AI agents, with their ability to write code many 100s of times faster than us, just bash through it. Furthermore, AI has no taste. It doesn’t smell code smells or appreciate the elegance of a well-designed abstraction.

If we no longer experience the pain (or the pleasure), what will motivate us to create new open source projects?

## Final Thoughts

I know this blog post seems all rather negative, I certainly don’t mean it to be. I am very excited about the potential of agentic AI and use it myself extensively. However, I don’t think we should be blind to the issues this is causing for open source.

I don’t expect open source  to suddenly disappear or die, in much the same way that I don’t think software engineers are going to cease to exist. You'll not find me writing a clickbait "Open source is dead, long live open source" blog post! But I do think that open source is going to experience a period of rapid and uncomfortable change.