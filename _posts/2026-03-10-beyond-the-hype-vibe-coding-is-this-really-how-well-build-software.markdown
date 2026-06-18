---
title: 'Beyond the Hype: Vibe coding – Is this really how we’ll build software?'
date: 2026-03-10 01:01:00 Z
categories:
- Podcast
- Artificial Intelligence
tags:
- AI-accelerated development
- vibe coding
- multi-agent systems
- software engineering
- AI coding tools
- GitHub Copilot
- Claude Opus
- Research Plan Implement
- RPI workflow
- rapid prototyping
- planning application demo
- AI in software design
- AI adoption spectrum
- Steve Yegge Gas Town
- autonomous coding agents
- developer productivity
- prompt engineering
- software architecture
- AI-assisted research
- legacy systems understanding
- engineering process
summary: In this episode of Beyond the Hype, I'm joined by Remi Van Goethem to unpack
  the fast‑evolving world of AI‑accelerated software development. From everyday autocompletion
  to emerging multi‑agent frameworks, we explore how AI is reshaping coding practice
  and where human engineering judgement still matters.
author: ceberhardt
contributors:
- rvango
image: 
---

<iframe title="Embed Player" src="https://play.libsyn.com/embed/episode/id/40344030/height/192/theme/modern/size/large/thumbnail/yes/custom-color/ffffff/time-start/00:00:00/playlist-height/200/direction/backward/download/yes/font-color/252525" height="192" width="100%" scrolling="no" allowfullscreen="" webkitallowfullscreen="true" mozallowfullscreen="true" oallowfullscreen="true" msallowfullscreen="true" style="border: none;"></iframe>

In this episode of Beyond the Hype, I'm joined by Remi Van Goethem to unpack the fast‑evolving world of AI‑accelerated software development. From everyday autocompletion to emerging multi‑agent frameworks, we explore how AI is reshaping coding practice and where human engineering judgement still matters.

Remi shares his recent experience rapidly prototyping a planning application using a Research–Plan–Implement workflow, highlighting how AI can transform early‑stage discovery, architecture thinking, and delivery speed. Together, we consider what this shift means for developers, architects, and CTOs as AI starts to generate more of our code, and whether vibe coding is a glimpse of software’s future or simply the latest trend.

## Useful links for this episode

* [Will the future of software development run on vibes?](https://arstechnica.com/ai/2025/03/is-vibe-coding-with-ai-gnarly-or-reckless-maybe-some-of-both/) – Ars Technica

* [Welcome to Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) – Stephen Yegge

* [I miss thinking hard](https://www.jernesto.com/articles/thinking_hard) – Juan Ernesto

* [Agentic Coding Makes Old Coders Young and Young Coders Old](https://scottrfrancis.wordpress.com/2026/02/13/agentic-coding-makes-old-coders-young-and-young-coders-old/) – Scott Francis

* [AI-Assisted Development at Block](https://engineering.block.xyz/blog/ai-assisted-development-at-block) – Angie Jones

* [Research → Plan → Implement Pattern](https://block.github.io/goose/docs/tutorials/rpi/) – Goose

## Subscribe to the podcast

* [Apple Podcasts](https://podcasts.apple.com/dk/podcast/beyond-the-hype/id1612265563)

* [Spotify](https://open.spotify.com/show/2BlwBJ7JoxYpxU4GBmuR4x)

## Transcript

*Please note: this transcript is provided for convenience and may include minor inaccuracies and typographical or grammatical errors.*

**Colin Eberhardt**

Welcome to Beyond the Hype, a monthly podcast from the Scott Logic team where we cast a practical eye over what's new and exciting in software development. Everything from Kafka to Kubernetes, AI to APIs, microservices to micro front ends. We look beyond the promises, the buzz and excitement to guide you towards the genuine value.

I am Scott Logic's CTO, Colin Eberhardt, and each month in this podcast, I bring together friends, colleagues, and experts for a demystifying discussion that aims to take you beyond the hype. In this episode, I'm joined by Remi to discuss his recent experiences of AI-accelerated software development. We discuss the broad spectrum of AI use from simple autocompletion to multi-agentic frameworks.

And more concretely, we discuss a recent project where Remi rapidly prototyped a planning application using a technique he calls Research, Plan, Implement. Finally, we ponder what this means for the industry and people within it. What it means for the developers, the architects, and the CTOs, as AI starts to write more and more of our code, and we ask whether vibe coding really is the future. We pick up the conversation with our thoughts on the latest developments in AI.

The thing that we really want to talk about today is vibe coding. And I guess from the hype perspective, is that the direction of travel of the industry? Is that how we're going to be doing software, going forwards? But before we get to that, vibe coding is a subset of what we do with AI and how we use it for coding. So, I was wondering from your perspective, are you keeping up with the latest developments? The last 12 months of AI have seen lots of model releases, lots of different tools and technologies. What are your thoughts on that? Are you, are you keeping up any particular highlights from your perspective?

**Remi Van Goethem**

I mean, keeping up is impossible. I don't think it's possible to keep up with all the different model releases, all the tooling, all the techniques. But yeah, I keep a, a high-level view of what's going on in the industry. And yeah, I think we are, if we talk in general about models, I guess in the last 12 months, I think we've reached a level where models are becoming extremely good at helping us.

For example, I'm a Claude user. I'm using a lot of their models. So mostly Opus, at the moment. But I cannot tell the difference between Opus 4.1 and Opus 4.6. I know that the metric tells me otherwise, but in general, they all work extremely well and, for the type of work I'm doing, I think I'll be happy with any of these these days.

**Colin Eberhardt**

Yeah, it does feel like, at some point, maybe six months ago, it got to the point where the leading models were all amazing, awesome, fantastic. And there was no real difference between them. They were all just amazing. I mean, did you get that feeling as well?

**Remi Van Goethem**

Yes. I think it was subtle to start with, and it accelerated a little bit, and as you said, I think it's probably the last six months where they're all super good. So, I remember like a year ago, everyone was talking about prompt engineering. It was super important to be good at writing your prompts super well; there are all sorts of techniques like the COSTAR and stuff like that. And I feel these days you can get lazy because the models are so good at filling the gap.

**Colin Eberhardt**

Yeah, it's strange, isn't it? Because it wasn't that they hit a certain percentage on a given benchmark. It was just that the capability reached some hard-to-define point, and almost it was, it's almost like AGI, in that it's not a terribly well-defined concept, but it will happen when enough people believe in it.

It feels like we've got to that collective belief with AI for software development.

**Remi Van Goethem**

But to be honest, I think they show that the models have plateaued a little bit. So, it doesn't scale any more to reach AGI in 2026 or 2027 without a breaking technique. So, I think all the different models have been, people training models have been, a bit more clever on how they do it.

**Colin Eberhardt**

Yeah, I was gonna say, getting back to the main topic of this discussion, there's a relationship between vibe coding and this tipping point that we've reached in the technology. So it's interesting; vibe coding as a concept, or at least the term is only 1-year-old, which I guess in, in AI probably actually makes it feel quite old.

So, the general concept of vibe coding is that you become completely detached from the code. You tell the model what you would like it to do. You observe the output. If it doesn't do what you want it to do, you simply tell the AI, make this change. Make this fix or add this feature.

When vibe coding first came out, was it something that you became aware of, or is it something you've only become aware of fairly recently? Did you dismiss it as that's a hipster, trendy thing, or did it make sense to you when you first heard it?

**Remi Van Goethem**

I think I was not an early adopter of it. As an architect, I don't code on a daily basis, I guess. So I  didn't try that, as an early adopter and probably at the time the model didn't have enough capability to be able to have multi-step reasoning to be able to reach the goal that you wanted to. They would forget their goal halfway through the exercise, I guess.

So, yeah. I, I think this is something that became much more possible, the last six months, I would say.

**Colin Eberhardt**

Yeah. Because even though, when Andrej Karpathy coined the term vibe coding, within the tweet or the post itself, there were notes of caution around how effective it could actually be, but I think, six months later, the model's become so much more powerful that his original vision of vibe coding became much more real.

Another thing we talked about was the adoption spectrum. So, at the zero level of adoption, you're basically writing code in exactly the same way that you've always written code. The next level of adoption, for example, is pair programming through GitHub Copilot. And then, there are various people who have published adoption spectrums, but I think the really interesting one, which was probably quite an extreme version of it, was the one published by the Gas Town creator. So that has a sliding scale that gets to the point where the top level is multi-agent, you never look at the code, your speed is the highest priority. I mean, how well does that fit your mental model of using these tools, and where would you sit on this spectrum?

**Remi Van Goethem**

I think it'd be good to speak for just a minute about this scale. It's quite neat, this scale from  Steve Yegge. So, he gave you eight different stages of adoption. And you can cut that into three different phases, like the one phase, you are still the pilot.
You fly, but you have a copilot with you. At stage two, you become a director, you're directing a fleet of agents. And at stage three, you are becoming like a factory owner, basically. And, if you think like stage 1, 2, 3, you're still using an Integrated Development Environment (IDE) because you care about the code. At some points, you give it all permission to do the modification in the code directly, but you're still reviewing the code, and you're still accepting the code.

When you become a director at stage four and five, what's interesting is that the difference between stage three and stage four is that you no longer look at the code. So, if you think of your IDE where you've got the agent chat on the right side, on the sidebar, now you've got the code on the sidebar, and you've got your agent chat in the main window. At stage five, you're supposed to no longer care about the IDE any more. You're straight away talking to the agent. It does the modification. You are not looking at the code anyway; you trust the output. The factory floor sounds a bit futuristic, but some people are already there.

It’s where you would start to use multiple agents at the same time. I don't know how people do that, how they can multitask to have multiple features in flight at the same time, but that's what stage six is. Stage seven is when you've got more than a dozen agents at the same time. That sounds scary to me. And stage eight is when you reach a scale so big that you need to build your own workflow, basically, like Gas Town.

**Colin Eberhardt**

Yeah, well, what I like about this scale, even if I don't necessarily agree with the specific steps on the scale, I think what it does very well is show that this is a spectrum and when vibe coding was first coined as a term, it gives the impression that you are either vibe coding or you are not vibe coding.

You are doing things the new modern way or the old-fashioned, handcrafted writing-the-code way. And in reality, it is a spectrum that there are levels of vibe coding, and Steve Yegge's scale goes, I'd say, almost beyond vibe coding. And it is a sliding scale. So, with that in mind, I mean, do you expect all software development to start pushing further and further up this scale of automation?

**Remi Van Goethem**

To me, it sounds like it seems to be a natural way at the moment. It's where the industry is heading. Some companies have started moving up in the scale. We've seen some companies like Square publishing how I think most developers are at stage five, and the second cohort is at stage six, so they're pushing towards the right side, where they manage a fleet of agents, basically.

**Colin Eberhardt**

At the moment, though, do you think there are obstacles to moving to the higher stages? So what I get uncomfortable about is when, using his term, the diffs scroll by, you simply don't look at the code. It feels like with the technology that we have at the moment.

You are still going to hit the same obstacles. And you mentioned this yourself when you talked about vibe coding, when it first came out, your feeling was that it worked for a limited period of time and then fell apart relatively quickly. Now I think you can vibe code, ignore the code entirely for a slightly longer period of time.

But I think you still get to the point where it's going to be a mess. Is that your experience? Is that your thinking?

**Remi Van Goethem**

Yes. I think it is the case if you don't have a workflow, I guess, or if you don't have some guardrails, and even with this, it’s not guaranteed that you get the result you want. We are working with models which are not deterministic anyway, so all the guardrails that you're gonna put in place, it might ignore them anyway.

**Colin Eberhardt**

So, you need some engineering approach. You can't just blindly direct the AI tool and expect it to create a good architecture or fault-free code.

**Remi Van Goethem**

Yes. I think when we value code, when the code becomes cheap, what's important is not the code, it’s the engineering process around it. And that's not cheap.

**Colin Eberhardt**

Yeah, very true. I mean, as an example, if you vibe code an application, your tool's not going to ask you, should we write some tests for this? Should we validate it? It will just build it. You have to exercise your human judgment there.

So, when it comes to how you approach this? So, we've talked about Steve Yegge's scale, and he created a tool called Gas Town, which is a relatively opinionated way to manage a fleet of agents to enable more vibe coding style approaches, more hands-off approaches, and there are other approaches like spec-driven development and so on.

How do you approach this if you, if you are vibe coding an application? How do you make sure that it does what you want it to do? That it still has enough of an architecture to be able to scale with new requirements and so on.

**Remi Van Goethem**

I guess it depends on what you're trying to achieve. Is it something that needs to go into production? Is it like a prototype or is it likea tool for your personal usage? There are all different needs for all of these different use cases. I code the same way as I work my day-to-day work.

I like to do some upfront thinking, which means that you probably wouldn't call that strictly vibe coding, I would say. Because, when you vibe code and you give full rein to the model, to the agent to fill the gap and do everything underneath, probably – and I guess if you are a bit opinionated on how you want to build certain interfaces or which quality you want to have on the application, what are some of the constraints – you can get results closer to what you wish, basically.

**Colin Eberhardt**

Yeah, that's a good point: the success or failure of taking a vibe coding approach can depend on how much thought and consideration you've put in ahead of actually typing in your first prompt to the AI tool. You're right, it can, it can feel very easy to just tell it to build my whole application, but from an engineering and an architectural perspective, we both know you'll probably miss the target by quite a long way and have to work hard to bring it back to where you actually want it.

Taking a concrete example, I know that recently you were working on a project where it was a tool that demonstrated a housing planning application process. And one of the goals was to demonstrate innovative new approaches to the planning process. So planning processes, like many, many processes, are pretty mundane. There's lots of form filling, there are multiple steps, and there's loads of room for potential innovation through the use of AI or just better software.  I know you managed to effectively vibe code a really cool demo in the space of a couple of weeks. How did you do that, and how does that illustrate your approach to vibe coding?

**Remi Van Goethem**

Yeah. I think that comes back to – how you approach vibe coding is – which technique do you use? There are multiple techniques. You could use certain techniques like, spec-driven development; we've got like Spec Kit, we can use BMAD, for example. These techniques are very good and have their strong points, but I like an approach called Research, Plan and Implement, which is the RPI method.

And this is, anyway, how you tend to work as an engineer. You always do some research before you plan and implement. And so I think it feels very natural. The RPI approach says that you need to do good research, you need to understand the domain, then you need to plan the work before it gets implemented.

And some content that I found was really nice about it. It says one line of bad research creates a thousand lines of bad code, one line of bad planning creates hundreds of lines of bad code. So yeah, where you should put your focus is on the thinking upfront, I guess.

**Colin Eberhardt**

So, just out of interest, with the Research, Plan, Implement approach. Is that an approach that you read about and thought, "That makes sense – I'll give that a go"? Or is that something that you just naturally found yourself doing because that's the way that you work, regardless of the use of AI?

**Remi Van Goethem**

No, I actually didn't know this thing existed at the time. It's just, it feels natural. So in my mind, you need to understand the domain. So for that, you're probably gonna be creating certain artefacts to capture the learning you've done, and you're gonna distil that into other artefacts.

That you can call a plan, for example, taking certain information. You distil that into something a bit clearer and more targeted to what you're trying to do, and then you use these different artefacts at different times of the process to create the outcome you want, basically.

**Colin Eberhardt**

So, talking through this example, then, the research phase. So, this was a tool; you had two weeks to create a demo for a planning application. Have you worked on planning software before?

**Remi Van Goethem**

The only thing I knew about planning was my neighbour, who was trying to do some modifications. So I received a letter from the planning officer to review. So, I only knew the workflow from the neighbour workflow of the planning application, but I knew nothing about the domain.

**Colin Eberhardt**

So, how did you do your research for this? How did you learn more about the domain to be able to create that domain understanding ahead of building something?

**Remi Van Goethem**

So, we had meetings with some experts at the beginning, so they just gave us some very high-level things: Who are the actors, what are the systems, and who are the Local Authority? That gave me a very high-level black box, but I didn't know how it worked inside. But they also pointed us at some existing open source encoding parts of the domain. So, what I've done is, checked out the code, I crawled the code, and I started doing some domain exploration by running the domain, basically.

**Colin Eberhardt**

And, the domain exploration – were you reading the code yourself, or were you leaning on AI to help with that?

**Remi Van Goethem**

The code was in Ruby on Rails. So, I'm not a Rail developer. I've never read that. But with the help of AI, I could get my way around it. So, I was able to run the application, and to seed the database to get the right data I needed to run the application.

So, if you think in terms of planning, you need to create some constraints, you need to have some data inside the product, in order to be able to run the workflow. But yeah, with the help of AI, I was navigating as if I knew what I was doing, basically.

**Colin Eberhardt**

Okay. So, I'm assuming then that AI was also a vital tool in this research phase, because I can imagine if you don't understand the planning domain, you are lucky in this sense that there were some open source projects that were quite similar to what it is you were wanting to build.

But even then, understanding a code base and a language that you are not familiar with, with a domain that you're not familiar with, I'm assuming previously that would've been a few weeks' worth of work to start understanding and analysing the code base.

**Remi Van Goethem**

It would've been several weeks of work. I can give you a flavour of things I've done, for example. In order to, to proceed through the workflow, I had to understand how the state machine worked because it needed to have certain events that move forward in order for me to progress in the workflow.

So, I've managed to extract the state machine using AI, doing some analysis. That became one of the artefacts that I used later, which helped me build up my understanding. Then I needed to move this state machine so I could zap the database directly using AI again.

Again, when I needed some realistic data, the model could generate it. If I needed to seed the database, the model could generate some realistic data sets. And yeah, that allowed me to basically understand the whole workflow. And to be honest, I've done a bit more than understand the workflow. We've been taking screenshots of all the applications as we were progressing, because we were making a lot of assumptions at the time, and we needed to get them verified with experts, basically, of the domain.

So, while we were building our understanding by mapping the workflow, we were as well annotating each of the screens to see where we could make improvements. And then we had to ask the expert, obviously, to resolve our assumptions.

**Colin Eberhardt**

Yeah, and this is a particular application of AI within software development that I don't think gets enough attention. So, you are able to rapidly research a code base and a domain with the intention of then creating a demo, which you used a vibe coding approach for. But this particular problem, understanding a code base and a potentially unfamiliar domain, happens all the time in software.

One of the main reasons why we struggle with legacy systems is the lack of understanding of that software system within the organisation itself. It feels like the approach you were taking here, whilst you were using it for a vibe-coded outcome, this feels important.

**Remi Van Goethem**

Yeah. I thought it was extremely proficient to be able to explore an API by using it, because sometimes there's a gap between the API documentation and how it behaves, and I've experienced that. During my research, I was able to run both applications, I was able to interact with them, I was able to ask questions about the code base, and I was able to extract, and there was some information; for example, I could understand what the as-is workflow is for a planning officer and use that to plan the to-be version of it.

**Colin Eberhardt**

And interestingly, in my opinion, when you're using AI for research purposes, it doesn't have to be perfect. Your tolerance for error is higher than your tolerance for error when you're using it to write production code. So, it feels like it can be even more powerful. You can give it even more latitude when you're using it for research tasks.

**Remi Van Goethem**

Yes, you, you're probably right because all that you're trying to do is reduce assumptions. So, it is not a right or wrong approach. You're trending towards the truth.

**Colin Eberhardt**

So, from collecting together some existing code bases, APIs running the application itself, through the use of AI, you were able to rapidly gain a good understanding of the domain and the planning processes. What was your next step? Did you then just vibe code a new version of the application, or was there something that happened in between?

**Remi Van Goethem**

Now there is definitely an in-between stage. So, you have the research, you have the plan before the implementation. And here, before the planning, I needed to get my assumptions resolved. So we needed to meet with the experts. And the best way for us to resolve our assumptions was to come up with this workflow with screenshots, annotated with assumptions that we put on the whiteboard and went through with the client. That was really helpful for them to be able to quickly annotate, tell us what was right, what was wrong, and where we were incorrectly making assumptions.

But by the end of it, we could take this big whiteboard workflow and turn that into a sequence diagram because these days, models are multi-modal. So, you can transform the artefact into something useful. And why is it useful? It’s because if I got the as-is flow, I can now use it to transform it into a to-be flow. I just have to inject an extra couple of constraints and explain my goals, and I can derive that and produce another artefact, for example. I can tell it how I want it to behave as a sequence before I feed that to a model to vibe code, basically.

**Colin Eberhardt**

Yeah, I just want to step back to something you mentioned very briefly that I still feel is quite important. You mentioned that you created the wire frames and then you got some expert input, and that still feels like it's a really important thing to do because vibe coding allows you to move very, very quickly, but you can still very quickly build something that's the wrong thing, or maybe 90% of the way there. And that final 10% is incredibly important. So, whilst you had very rapidly learned the domain, you weren't an expert at the end of like three days of AI research.

**Remi Van Goethem**

Yeah, that's correct, and I think that's, that's the thing with all this vibe coding trend – the only way for vibe code to be very fast is if you are the expert yourself of the domain, if you're the product manager, if you are the architect, if you're all these people at the same time. Otherwise, you need to get the input from the experts.

**Colin Eberhardt**

That's an interesting point, and it doesn't mean that you are all of a sudden a lot slower, but you do have to be very intentional about finding the right time to get the feedback and getting the right level of feedback. Yeah, that's really interesting. So you've gone through the planning process, and you are now onto implementation.

What did that look like, and how long did that take?

**Remi Van Goethem**

The implementation phase was the most fun part, I would say. It is more fun for me because I tend not to code very often any more in my day-to-day work. And I could build some cool things very quickly. So, this phase, I've had my research, which I've distilled into several artefacts, super-high-level sometimes, like design principles, high-level constraints, very high-level things that I can invoke at certain times of the process, to say, okay, be careful of this, and, like that, I could guide the code towards where I want to be, basically.

**Colin Eberhardt**

How did you know that having a design principles document was the right way to do it? Was that just a guess? Did it just feel like the way to approach this problem?

**Remi Van Goethem**

I deal with models the same way I deal with colleagues. I don't come up with a full design where everything is wrapped up, and people just have to code. This is not how it works. You have to provide some constraints, some guardrails, some direction, some opinionated choice, and then you let the engineer fill the gap.

And I feel this is the sweet spot with models; you can just guide them on what you think is the right level of detail and let them fill the gap.

**Colin Eberhardt**

That's really interesting because that reflects a more negative experience that I had using Spec Kit, which is quite an opinionated approach to specification-driven development. I dunno if you've used it yourself, but it has a very, I mean, to a certain extent it reflects the Research, Plan, Implement, but it does it in a very detailed, very opinionated fashion.

And to your point about the design, it creates Markdown files with ASCII-art-style images of every single screen, and the plan stage has code snippets in it. It tries to steer the model with a very high level of specificity. And to your point about working with human beings, it's the level of detail you would never give to an engineer.

**Remi Van Goethem**

Yes, I agree with you. I've looked at Spec Kit, and I was not really convinced, I would say, because it feels extremely heavy, it feels like Waterfall, really. You get a real level of detail super early, and the Spec Kit approach is supposed to be that you should never throw away your spec, it's as important as the code.

But that means you're supposed to review the spec and review the code, and with the models, they don't always respect it. It feels like too much effort.

**Colin Eberhardt**

It does, and something else you mentioned that you have experienced in the past 12 months, which I've experienced as well, is that 12 months ago, you had to be a bit more careful about your prompting. You had to engineer it a bit more, whereas now, it feels like they just understand you so much better.

It feels like we have to engineer our prompts less. We are just steering them at a high level, and Spec Kit feels like it's pushing in the wrong direction. It's not capitalising on the gains that we've had in the past six months.

**Remi Van Goethem**

Yeah, I think RPI is probably the middle ground here.

**Colin Eberhardt**

Yes, and it feels like with RPI, you can describe it in just those three words. You don't have to research a specific way. You don't have to plan in a specific way. You don't have to implement in a specific way. Personally, I like patterns that you can describe in a few words or a sentence, because I think that gives you the freedom and the flexibility that you need to adopt it efficiently in your given context. Anyway, getting back to your actual vibe coding, you said it was really fun. I mean, why? Why was it so fun?

**Remi Van Goethem**

I think it's this prompt-to-outcome loop. I think it's high dopamine, probably. You get a reward very quickly and you see the application being built, step by step. I said step by step, because I didn't build the whole thing in one go.

**Colin Eberhardt**

And when you were doing this, this wasn't a fleet of multi-agents, this was a single agent. Was it Claude Code or GitHub Copilot, or…?

**Remi Van Goethem**

It was Copilot at the time.

**Colin Eberhardt**

Yeah. So, given how quickly you moved, what do you think of the whole multi-agent approach? Personally, I feel that I find it hard to keep up with a single agent, and steer it either by planning or steer it by correcting after it's produced it. I find that hard work. I mean, I'm impressed that some people are going down the multi-agent route, but that just feels too fast for me.

**Remi Van Goethem**

It depends on what you mean by task. If you're talking about feature level, probably the bottleneck is gonna be the planning. If you talk about tweaking the CSS or fixing this bug, you can probably do that.

**Colin Eberhardt**

That's true. Yeah.

**Remi Van Goethem**

But I'm the same as you. I don't think I can multitask. I want to make sure that what I've been working on is completed, and to the level I want.

**Colin Eberhardt**

Yep. So, I guess, the final thing I want to talk about – and I think it naturally follows on from your feeling it being fun to vibe code this application – is the excitement of building something really fast. I'm seeing a lot of blog posts and very well-written blog posts recently about people finding this new way of working quite uncomfortable.

There was one I read a while back about mourning the craft. People are struggling to come to terms with this quite different way of working. And I mean, it would be impossible to go through all the different blog posts, but one that jumped out at me was one that was titled, ‘I Miss Thinking Hard’, and they described people as either Builders or Thinkers.

So, Builders are people who get that dopamine hit from creating software, whereas the Thinkers are the ones who get the excitement outta the code and the crafting it. Does that match your mental model? Do you, do you feel more like a Builder or a Thinker? Do you think that simplification works?

**Remi Van Goethem**

I like a bit of both, but I would say I’m probably more geared toward the Builder side. I like to see the outcome. I like to solve complex problems, and these days, I like to solve business problems. How it's done is probably not as important to me these days. But I think everyone's gonna be different. What is your view on that?

**Colin Eberhardt**

Yeah, I think it's a good mental model for starters. What I found interesting is that the types of things that I've been building as a hobby have changed. So for me, I've been doing software professionally for 25 years, but I've always enjoyed the craft of software itself.

So I've always had side projects, and if I look back five or six years ago, I was doing a lot with things like WebAssembly and having fun, building things like emulators. I was the Thinker back then. I was building things for the fun of building it, and with the emulator, I never played any games on it.

I just wanted to build the thing 'cause it's fun. Whereas now my hobby projects are, I'm building a thing for logging carting sessions and so on. I'm actually creating an application where the code itself is boring. It's a crud-style application. But I enjoy the outcome. I'm now building things that I use, whereas previously, I built things that I didn't use.

It's really weird. I feel like I've leaned more on the Builder side of things because vibe coding  has allowed me to build more.

**Remi Van Goethem**

The cost of building custom tools for yourself has never been lower than now.

**Colin Eberhardt**

Exactly. So I think this technology has turned me into more of a Builder than a Thinker. Well, that sounds bad. I'm sure I still think, but there are so many of these blog posts; you pointed out another one to me that agentic coding makes old coders young and young coders old. And what I found really interesting about that one is, it looked at the programmers at different stages in their career, and the people that are at a later stage in their career – they've been an engineer for a while, maybe they're an architect, maybe they're a manager or a CTO or what, whatever else, and they don't have much time for writing code or haven't written code for a long time – that's the group that seems to be really taking to this technology.

It's the people who are in between the people who are really quite experienced, but still have a deep connection to the craft. Those are the ones that are struggling.

**Remi Van Goethem**

Yeah, I agree 'cause I think people at the later stage of their career, they've moved up the abstraction layer, and they're already doing a lot of delegation, so it feels very natural to use AI the same way as they do anyway. But I think for people who are quite early in their career, they're probably gonna be adapting super-quickly to this new paradigm.

So, yeah, it leaves maybe the people who are mourning the craft itself, because I think it is true – if you care very much about the code itself, it is at risk of being commoditised today, so yeah, this is a risk for sure.

**Colin Eberhardt**

Yeah, definitely. So, I guess that gets us to the ultimate question that we're trying to answer. Do you think vibe coding is the future?

**Remi Van Goethem**

I think there are multiple levels. If you're talking about like prototyping, yes, this is definitely the future; you can get something very quick. You don't need to go for low-fidelity stuff any more; you can show the real thing very quickly. For research, yes, a hundred percent sure; it's super useful.

But I don't buy into the “anyone can code” vibe, because it's not just about coding, it's about engineering. And I think what vibe coding does not achieve at the moment is the engineering thinking; so, I don't think we are here yet.

**Colin Eberhardt**

Yeah, and I completely agree with you. I think vibe coding itself has a fantastic future, and we'll find more and more places that we can use it. But I don't see it as the ultimate destination of all software development at the moment. And that's the thing that I think is a big unknown. I know you mentioned that your feeling is that the model development has maybe slowed down and plateaued; if there's a point where it starts to really understand architecture, maybe vibe coding will be able to cover a lot more of what we are doing.

**Remi Van Goethem**

Yes. I think, as always, the thing that it doesn't understand is the need of the business, for example, or human needs. And we need to be able to have this human intuition, I guess, to understand what matters.

**Colin Eberhardt**

Absolutely. And at the moment, that's one part of the puzzle that they haven't solved at all through the use of AI.

**Remi Van Goethem**

Doing something is cheap, but knowing what to do is not.

**Colin Eberhardt**

Yeah, absolutely.

And that brings this month's episode to a rather abrupt halt. I must have a word with Paul, our editor(!). In truth, Remi's final statement that with vibe coding, doing something is cheap, but knowing what to do is not, was so powerful that there wasn't much more either of us really wanted to say on the matter. If you've enjoyed this episode, we'd really appreciate it if you could rate and review Beyond the Hype.

It'll help other people tune out the noise and find something of value, just like our podcast aims to do. If you want to tap into more of our thinking on technology and design, head over to our blog at scottlogic.com/blog. So, it only remains for me to thank Remi for taking part and you for listening.

Join us again the next time as we go Beyond the Hype.