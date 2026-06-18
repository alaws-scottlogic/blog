---
title: 'Beyond the Hype: Is AI taking the fun out of software development?'
date: 2026-04-01 00:01:00 Z
categories:
- Podcast
- Artificial Intelligence
tags:
- AI-assisted development
- software engineering
- developer productivity
- agentic workflows
- GitHub Copilot
- open source contribution
- debugging skills
- developer experience
- AI in software
summary: In this episode, I'm joined by Dean Kerr and Amy Laws to discuss 'The Experiment'
  – a four‑week study we ran to explore how AI really affects software development.
  Instead of synthetic benchmarks, the project team tackled genuine issues in an open‑source
  project, alternating between AI‑assisted work and going completely 'cold turkey'.
author: ceberhardt
contributors:
- alaws
- dkerr
image: "/uploads/BeyondTheHype---green-and-yellow---episode-32---social-3de887.jpg"
---

<iframe title="Embed Player" src="https://play.libsyn.com/embed/episode/id/40603570/height/192/theme/modern/size/large/thumbnail/yes/custom-color/ffffff/time-start/00:00:00/playlist-height/200/direction/backward/download/yes/font-color/252525" height="192" width="100%" scrolling="no" allowfullscreen="" webkitallowfullscreen="true" mozallowfullscreen="true" oallowfullscreen="true" msallowfullscreen="true" style="border: none;"></iframe>

In this episode, I'm joined by Dean Kerr (Lead Developer) and Amy Laws (Developer) to discuss 'The Experiment' – a four‑week study we ran to explore how AI really affects software development. Instead of synthetic benchmarks, the project team tackled genuine issues in an open‑source project, alternating between AI‑assisted work and going completely 'cold turkey'.

The contrasts were striking. Amy’s AI‑free period exposed how dependent everyday development has become on instant summaries and contextual answers. Meanwhile, Dean found that adopting a simple agentic loop (Analysis → Implementation → Reflection) helped him make better use of AI rather than blindly accept its output.

Together, their experiences reveal a discipline in flux: developers gain speed and support from AI, but also confront questions about craftsmanship, learning, and where the fun in software now sits as the tools reshape both workflow and mindset.

## Useful links for this episode

* [Analysis → Implementation → Reflection – a practical technique for issue resolution with agentic AI](https://blog.scottlogic.com/2026/03/05/analysis-implementation-reflection-practical-techniques.html) – Dean Kerr, Scott Logic

* [Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) – METR

* [SWE-bench](https://www.swebench.com/) – SWE-bench Team

* [Agentic Engineering Patterns – Red/green TDD](https://simonwillison.net/guides/agentic-engineering-patterns/red-green-tdd/) – Simon Willison's Weblog

## Subscribe to the podcast

* [Apple Podcasts](https://podcasts.apple.com/dk/podcast/beyond-the-hype/id1612265563)

* [Spotify](https://open.spotify.com/show/2BlwBJ7JoxYpxU4GBmuR4x)

## Transcript

*Please note: this transcript is provided for convenience and may include minor inaccuracies and typographical or grammatical errors.*

**Colin Eberhardt**

Welcome to Beyond the Hype, a monthly podcast from the Scott Logic team where we cast a practical eye over what's new and exciting in software development. Everything from Kafka to Kubernetes, AI to APIs, microservices to microfrontends. We look beyond the promises, the buzz and the excitement to guide you towards the genuine value.

I'm Scott Logic's CTO, Colin Eberhardt, and each month on this podcast, I bring together friends, colleagues, and experts for a demystifying discussion that aims to take you beyond the hype. In this episode, I'm joined by Amy and Dean, who have been undertaking an experiment to quantify the impact of AI on software development.

And yes, they found that AI resulted in an increased velocity. However, through this experiment, we learned much more about the broader impact AI is having on software development. And the impact on the human beings who are still an important part of this process. This impact is leading us to ask questions about the future of this craft, and ultimately, here, we ask whether it's taking the fun out of software development.

We pick up the conversation by discussing what this experiment was and why we undertook it in the first place.

### Introduction to The Experiment

**Colin Eberhardt**

We sort of came round to this discussion from something the two of you have been doing, uh, within Scott Logic, uh, recently, that internally we, we seem to call it by the shorthand of The Experiment, which makes it sound really quite grand. But Dean, for the benefit of the people who have no idea what The Experiment is, it would be great if you could describe what the two of you have been up to recently and why.

**Dean Kerr**

Yeah, so we've got a small sort of AI Incubator team within Scott Logic, and we were looking at running an experiment, as you say, into the effectiveness of AI when it comes to, uh, development. Both from a sort of a qualitative standpoint and also from a quantitative standpoint. So, how much faster does it make you, but also, and it could be more importantly here, how does it make you feel, and does it improve or sort of reduce job satisfaction?

And we ran this experiment over four weeks. So, we had two phases of The Experiment primarily. We had a two-week upskilling phase where we got to grips with an open source library of our choosing. We preselected 10 issues from that open source library. Uh, making sure that the issues were sort of real-world issues that we'd typically encounter in our role as software consultants.

So, issues that are relevant to us. And then, the second half of The Experiment, the latter phase, was actually going away, pairing up and then individually within those pairs, working through each of those 10 issues using an approach. One approach was actually " cold turkey" – no AI whatsoever – which was quite interesting; some team members who had used AI previously are now going back to no AI, which has an interesting viewpoint there. And then the other approach was using what we termed basic AI. So, in this case, it was what we get from GitHub Copilot on the sort of bare-bones subscription, which is roughly, I think $20 a month per seat. And we picked a sort of free model. Which was GPT-5 mini.

**Colin Eberhardt**

Cool. So I guess there are lots of people and organisations trying to measure the impact of AI, but The Experiment, as we call it, does feel a bit different. A lot of the benchmarks that you see published tend to be more clean-room environments. Uh, often they are measuring the effectiveness of just the AI itself, not AI plus a human being.

It feels like this experiment is a little bit more of a better reflection of the real work of a developer in a complicated and potentially unfamiliar environment. From your perspective, Dean, does it, did it feel like a good reflection of real work?

**Dean Kerr**

I believe so. I think it definitely felt closer to home. Like you said, there are plenty of experiments out there that we could lean back on that are fairly clean room. They're actually quite wide-scale as well, whereas we kept ours sort of smaller and simpler, and I think more focused.

Importantly, so that we have evidence from these experiments that is actually relevant to us and our domains that we typically work in as well.

### Real‑World Workflows: Open Source, Quality and Benchmarks

**Colin Eberhardt**

So why pick an open source project over just some internal code base? What was the thinking behind that?

**Dean Kerr**

I think there were two caveats to picking an open source project, one of them being the ability to actually contribute back to open source. So we ended up picking a mock service worker, and the plan there is to contribute back to some of the libraries that we ourselves have used professionally in our day-to-day roles. So it's nice to contribute back there. But I guess secondly, there was also a sort of proof of a mechanism in play here, so that a lot of the experiments, you know, run an issue for you, the standard software development lifecycle. And we could actually use as proof the fact that the issues we worked on were actually reintegrated into a mock service worker or the open source library as a sort of a gold marker or gold standard to say, “Hey, the work we did, it wasn't just slop.” I know there was a lot of, uh, talk recently around a lot of open source libraries just getting a load of pull requests put up. But we wanted to ensure that our work was relevant and appropriate.

**Colin Eberhardt**

Yeah, that's really interesting because the benchmarks that the organisations that are developing the foundation models, they have a benchmark and some of them are relatively real-world things like SWE-Benches, a bunch of GitHub issues, and their goal is to typically make a suite of tests pass.

So, they're demonstrating that it's functionally correct, but there isn't really anything that assesses the quality. Whereas not only are you doing something of actual value by fixing a real-world issue, the fact that the quality gate is outside of the team means a maintainer has to go, "Yeah, I'm, I'm happy with that."

That's a real rubber stamp that the solution that you came up with, whether you used AI or not, was of good quality.

**Dean Kerr**

There were a couple of issues we encountered as well, where we had maybe two or three solutions that were all equally valid, but it was more a matter of preference which one would be accepted. And it was almost sort of second-guessing what the library owner themselves would prefer. So, each of these three solutions, they all tackled the issue slightly differently, and that meant trade-offs in different ways for the mock service worker.

**Colin Eberhardt**

So, one of the things that I found interesting about this experiment was not the obvious. The spoiler is, funnily enough, AI makes you faster. And I don't think anyone's surprised by that. I think we came up with a factor of 1.9. Could have been any number, really. We knew that it was, or at least we hoped that our experiment was going to demonstrate that you're faster, because we certainly feel that. What I found more interesting and quite surprising is some of the things that, that you as the team learned along the way. And I think some of the most extreme learnings and the most interesting learnings came from the team that wasn't allowed to use AI at all. What, what you called the "cold turkey" team.

### Cold Turkey Begins: Rediscovering Pre‑AI Development

**Colin Eberhardt**

Now, Dean, you were lucky, you got to use AI even if it was the old, slightly rubbish version. But Amy, I'd love to hear more about your experience, because you were in cold turkey land, and I know you worked alongside Andy. And what I found really funny was that he, he went, he went deep, he tried to eradicate AI from his daily personal life as well.
What, what, what was it like having AI taken away from you?

**Amy Laws**

Yeah, so I think like coming into this, um, obviously being on the, um, AI Incubator team, we're kind of encouraged to explore and use it more heavily than other people. So, it really was kind of a contrast having to go from using AI and experimenting with it to not using it at all. So, when we say no AI, Andy and I really tried to do everything we could to avoid AI. So, we disabled it in our IDEs because what I forgot is that it's so integrated now that, although I wasn't actively opening the Copilot chat panel, the autocomplete was still on, so I had to fully disable it. The same, even doing kind of Google searches, which is kind of your fallback, the AI search automatically pops up at the top.

So, you are having to scroll straight past it, and it's one when you're actively trying to avoid it, you realise just how ingrained it has become in everything that we do. So, that was kind of a bit of a learning curve, I guess, reverting to an older way of working, of picking up, going back through your Stack Overflow and forums and reading docs and those kinds of things that I've not had to do for quite a long time.

**Colin Eberhardt**

What was it like going back to Stack Overflow? Because I've seen the statistics that the Stack Overflow traffic has dropped considerably, so we know fewer people are using it, which makes sense, but for the few people that are using it, so you were forced to use it, what was it like going back to it? Is there a feeling that information is now lacking because Stack Overflow only exists because of an ongoing question-and-answer flow? But what's it like there now?

**Amy Laws**

Yeah, definitely. Like, I guess when I was using it a couple of years ago, I would kind of automatically discount older answers or take them with a pinch of salt because things in tech move so quickly. Something that was answered five years ago might not necessarily be relevant anymore. But that's really hard to do these days because, as you said, the response rate and, I guess, people asking questions on it, are dropping so rapidly. We just found that a lot of the things we were Googling or like searching on there, there just weren't modern responses, and it may not be compatible with the versions of the libraries we had and that kind of thing. So, I definitely found myself having to search a lot harder on it than I would've previously.

**Colin Eberhardt**

Yeah, so it is weird. We are, We are getting to a point where, without AI, it's fundamentally harder to find the answers.

**Amy Laws**

Yeah, I definitely agree with that. And I guess, I think I've lost the skill a little bit as well. Um, so I've not had to search through like documentation for quite a long time, and I think there's kind of a skill and a nuance to that, that you kind of have without realising it.

**Colin Eberhardt**

Yeah. So, taking a step back, when you talk about AI-assisted software development, most of the time you think about AI writing the code.

### Losing Old Skills, Missing New Tools

**Colin Eberhardt**

And another thing that I found really interesting in this experiment was that so much of what you missed was not the fact that it wrote the code for you. It was all the other things.

Can you talk about that? I mean, you've already talked about searching for answers to questions, but there were a lot more examples than that, weren't there?

**Amy Laws**

Yeah, so a big one for me was kind of summarising information. So, it's already been spoken about, but we worked on open source issues. But what we did with that is we actually went from the oldest ones on the backlog to the newest. So, a lot of the issues that we had were quite old. Some of them had very, very lengthy comment threads; some of them had over 60 comments. And a lot of that was noise, so people saying, “Oh, have you tried this workaround? This might have been fixed in this version.” No, it hasn't. And all that kind of information that isn't really that helpful a few years on. 

Trying to kind of understand that entire comment thread and retain the important bits of information was quite difficult, especially when our job involves things other than just coding. So I'd kind of get myself up to speed with it and then get broken off to go to a meeting or something, and then coming back and trying to get back into that thread and what was relevant and what wasn't was quite hard.

And I felt it was frustrating to know that if I had AI, I could have just thrown that issue into AI and got a nice summary. And I think that's one of the things of having had it removed, you realise what you're missing more.

**Colin Eberhardt**

Yeah, absolutely there. And thinking about how I use it and to, to your point, things like through Google search, I mean, often if I'm looking for something, I still use Google pretty much in the same way I'm trying to find a thing. But if I'm asking a question, more often than not, its AI-generated summary will answer that question. And I don't have to navigate to a different site. It's changed the way that I work without me intentionally, choosing that change or even acknowledging that's the change that's taken place.

**Dean Kerr**

I guess it's one of the, sort of, the life cycles of the internet I've seen where it started with IRC (Internet Relay Chat) and message forums and things like Stack Overflow might be the next sort of format to sort of be cannibalised, really by the next format, which may well be just an input box where you ask AI.

**Colin Eberhardt**

Yeah, and that's a massive rabbit hole that I, I'm not sure we'll even go down because I, I couldn't work out, well, I can't work out what the future might look like because we know that the AI was trained on that data set, that's what makes it so powerful, and the feedback loop has gone. If we are not asking questions, what does the AI train on? As I said, we'll not go down that rabbit hole 'cause I have no idea what's gonna happen.

But getting back to some of the things that you mentioned about using AI to help you answer questions, to summarise information. What I find really interesting about that is that there's a lot more tolerance for error in the AI. We, we focus a lot on how much code can it emit? How, how good is that code? And, and if it's not good, some people sort of reject AI for software development to a certain, to a certain extent because they don't think it writes quality code.

Whereas when it's summarising an issue thread or you're just having a conversation with it, it feels like you can be a lot more tolerant. When you were using it to summarise issues, did you think about what the quality of the AI summarisation is, or was it just that it felt good enough?

**Dean Kerr**

Yeah, I guess for me it did feel like it did a pretty good job. Like Amy mentioned, there are pretty long comment threads in some of the issues, and there is the case of, yeah, do you trust the summary because things will get cut out, and the AI is making a judgment of what things are relevant and no longer relevant.

But looking, you know, I had a look afterwards, 'cause the, the raw sort thread is there. And it did seem to do a pretty good job at that. I think what's interesting is, I guess it's, in this case, it was a GitHub issue, but it could equally also be a Jira issue or a Trello issue. And one thing I didn't really get to explore, with the GitHub issue, is using the sort of multimodalness of modern AI now, where in Jira you typically have screenshots and, it could be error messages, or stack traces that you can all feed to the AI to summarise as well. So, I think I did a good job with the textural summary. I'll be really interested in terms of next, if I feed it more than just one piece of data, how it would actually do in terms of summarising all that as well.

**Colin Eberhardt**

Yeah, I guess this gets into, we've talked a bit about going cold turkey, and how that really made you sort of reflect on how much you use AI, and to a certain extent, we're all becoming dependent on AI. Another thing I found interesting in the experiment was from the team using AI, and that it wasn't a case of, oh yeah, roll up our sleeves, we are using AI.

### Agentic Loops and Structured AI Workflows

**Colin Eberhardt**

Dean, you talked about the approach that you are using and, and you, you, you sort of described it as a particular pattern of Analysis → Implementation → Reflection. How did you get to that point? Why? Why did you sort of feel the need to almost formalise your own approach?

**Dean Kerr**

There's been a lot of sort of literature recently that talked about closing the feedback loop with agentic AI and the sort of improvements that can be made through that. And, um, yeah, there's some, for example, some recent posts on porting across things as large as web browsers or parsers with relative ease and swiftness as well.

So, I thought if that could work for sort of a larger-scale project going, I guess from a relatively greenfield, ground zero to a fully working application, I felt like it would be equally valid for just picking up a single issue as well. So yeah, I think putting a little bit of effort in at the very beginning, uh, knowing that I had to tackle 10 issues, to set up a, a lightweight harness that Analysis → Implementation → Reflection, I felt that that would pay dividends.

So, and I think it did in the end, uh, the, the Analysis phase, looking at the issue, summarising the thread for me, giving me the chance to interject, I didn't agree with what it had summarised or if it was a bit off in, in, in some respects to its understanding of the issue. I gotta remember I was using the free model from around August, so I think the capabilities of models have jumped since then. So, um, I think it didn't get things as right as the premium models. So having the ability to interject was quite useful. The implementation phase as well, where I could set the model off now that I have sort of double-checked its understanding, let it run implementation against some test cases that were built during the Analysis phase and in a sort of red/green, uh, loop, uh, run into those test cases pass.

**Colin Eberhardt**

So, was that actually an agentic loop? Did you basically instruct it once you've done your analysis and you've built up a test suite? Do you then basically say, right, now you can solve the issue.

**Dean Kerr**

Yeah. And, if it was a feature, implement the feature, or if it was a bug, you know, implement the fixes in it.
I think you read in these articles, and it all feels very grand and formal, but it is really just prompting the agent to run tests until they pass. It's as simple as that, really.

It doesn't have to be a heavyweight, super complex harness, uh, you can get away with a, with a simple prompt, really just to say, use red/green.

**Colin Eberhardt**

Yeah. And that, that's something I find really interesting about AI and agents as a tool, that they're not in any way opinionated. And by that I mean they don't have an opinion about how you should use them. And I dunno, Dean, whether you've, whether you've had the time to think about how you used these tools in the past, was it more because we were running this experiment, you thought, I need to have a think about how I approach this. I've heard of agentic loops. I, I believe that to be a productive way of working. I'm gonna spend a lot of time working out how I approach the construction of an agentic loop. I mean, was that quite new to you, to spend that much time considering how you use this tool?

**Dean Kerr**

I think a lot of it's fairly new to a lot of people. It moves that quickly. And that was the, I guess, the beauty of the first phase of the experiment, where you get two weeks to do upskilling. A lot of studies, uh, as you've seen elsewhere, don't give anyone any time to get to grips with the approach, which is, you know, what model you may be using, what tooling, be that GitHub Copilot or Claude or others. And then the approach being agentic AI, for example. So, having the time to actually experiment and see what does and doesn't work for a particular approach gave me the time necessary to fall into that sort of feedback mechanism, which is probably one of the latest styles of approaches that people are currently doing at the minute.

**Colin Eberhardt**

Yeah, I think this one was inspired, I think, by a study by METR, where they were looking at the impact of AI, I think, on open source maintainers. And what they effectively proved was that people who are experienced with AI are better at using AI. That was sort of paraphrasing it. But Amy, what are your thoughts on Analysis → Implementation → Reflection? To a certain extent, does that potentially reflect the way that you, as a human being, approach the problems?

**Amy Laws**

Yeah, I think so. Obviously, we didn't have the AI to help me with it, but I think it is kind of an extension of our natural workflow. And I think from using AI for other things, um, the more and more I kind of treat it in the same way that I would work without it, I have found it is more effective.

I guess, kind of naturally, the Reflection part is the most important. And I would naturally do that before I put something up for PR (Pull Request). I would kind of sit and like almost review my own PR before I put it up. And I think probably with AI, I've developed a bit of a tendency not to do that quite as much or not be quite as critical.

Whereas I think going back to not using it, I made sure that I really, really understood what every line of code was doing and that I was kind of happy with it. And I think that level of understanding is something that I didn't realise that maybe I've become a bit more lenient with.

**Colin Eberhardt**

Yeah, I think you make a great point 'cause it's, it can be really quite hard to work out how you should be using AI, and it's easy to think, oh, I'm using it wrong, but I use a similar approach. I, I think, how would a human being do this particular task, whether it's software development or something else, and more often than not, that's a pretty good path forward.
On the reflection side of things, when you mentioned that Dean, I realised I don't think I've ever done that. I don't think I've ever, when using AI to write code, asked it, “Why did you do that? What was your reasoning for doing that?” That was really eye-opening for me. I dunno whether that's a thing that people typically do.

**Dean Kerr**

I think with a lot of things, I guess it is just drawn from experiences before AI. As a software developer, if a junior team member put up a PR, you'd ask these questions, in your head at first, “Okay, a solution's being proposed to me, but what are the alternatives and why did they get ruled out”, so to speak?

So, it's a natural tendency to reflect after you've done a bit of work. And I think with AI, there's the, I guess, there's also the tendency to just submit whatever generates immediately, and that always feels a little bit wrong to me. I like to sit and sort of study and stew on a particular solution, just for a little bit until I have the confidence and the, I wouldn't say bravery, but to put it up for review by others.

**Colin Eberhardt**

I wonder if there's almost a psychological OB obstacle here, because I don't think AI genuinely thinks, and part of me is almost reluctant to ask it, “Why did you implement it this way? What other options did you consider? And then asking it, “What other options did you consider?” I don't think it really considered options. But it sounds like you could ask it those questions and still get a valuable output.

**Dean Kerr**

Yeah, it's, it's treating it like I guess a fellow developer. It's it is a Large Language Model at the end of the day, but, yeah, talking to it as you would a human can, in a weird way, the closer you bring it to your old or current ways of working, the better you can understand the output half the time.

**Colin Eberhardt**

And again, this is the weird thing about the tool, I think sometimes understanding that it's a large language model, understanding the basics, like what a prompt is, context engineering, context length. I think that's really helpful. But then, sometimes that actually understanding what it is feels counterproductive. Sometimes, you just have to suspend disbelief and pretend it's a human being. It's very weird.

### The Future of AI Work: Autonomy, Architecture and Senior Skills

**Colin Eberhardt**

So, just taking a step back, this is a difficult one, but where do you think this technology's heading in the future? Do you think we are gonna spend a lot more time effectively talking to AI and getting AI to write our code for us? It feels almost inevitable. What are your thoughts?

**Dean Kerr**

I think for the vast majority of use cases it's gonna move on that sliding scale towards full autonomy, really. At the minute it's sort of AI augmented development, but, um, I guess the step next after augmented is more inclined with autonomous. So, moving away from interjecting as much and perhaps just being more of a reviewer rather than a co-creator of software.

**Colin Eberhardt**

Yeah. And Amy, as an example, outside of this experiment, does that reflect your day-to-day? If you're writing code for whatever reason, are you typically spending more time thinking about how you can encourage AI to write the correct code or create a harness or an agentic loop around it?

Is that your mindset these days?

**Amy Laws**

Yeah, I think it is. So, I'd probably describe myself at the minute as using AI to maybe get 90% of the way to a solution. So, kind of using it to do a lot of the boilerplate and then being able to refine it on top. But to get that boilerplate to a good quality, as you said, there are other considerations that you've got to put in.

So yeah, setting up feedback mechanisms in a way that the AI can usefully iterate, if that's something that you want to do. I think I spend more time defining my specs at the start and kind of thinking really carefully about what it is I want to build, because I know that I can take the leaps a lot faster.

So, having that defined upfront is something that I'm having to do a lot more. I guess previously you would kind of build a little bit and then maybe think about what the next steps were, whereas now it feels like you've got to think two or three steps ahead because you don't know how fast you're gonna be able to jump between them.

**Colin Eberhardt**

Yeah, and that's the interesting thing, is that it feels like a very different type of skill, and more often than not, we associate that particular skill with being relatively senior and experienced within software. Dean, I can imagine that, well, you described it yourself, a lot of the experience you've used to help you make the most of AI is the experience that you've gained from working in software for a while.

And Amy, I know your, your situation's slightly different in that most of your career has been with AI. For the people who are joining now, where AI is the tool that they will immediately be given, how do they gain those skills that you think are important, and I think we all agree are important to being successful with AI?

**Amy Laws**

Yeah, I think that's a really hard one, because it's something that is quite a new challenge. I think I've relied a lot on the skills that I first learned when I was learning to program. Kind of debugging is becoming really important. Often, I found that AI is not great at helping debug things.

So, I think it probably is a case of challenging yourself to maybe not go completely cold turkey as we did, but maybe step back from the tools a little bit and make sure that those fundamentals are there, because I think you need both ends of the spectrum. You need to be able to get into the nitty gritty and, I dunno, debug a hard issue or resolve an issue that AI can't, but you've also got to be able to do the, like other extreme, as Dean said, of working as a more senior team member and I guess almost like treating the AI like a junior developer. And I think it's gonna be quite a hard one for people to learn both of those ends in parallel.

**Colin Eberhardt**

Yeah, I agree. I think there's gonna have to be a really considered change to how people learn because it would be all too easy to give someone inexperienced an AI tool and see them suddenly be very productive and think, “Okay, there's no need for them to learn anything.” For people who are new to software development, I think we're gonna have to intentionally slow down and make sure they do learn some of the skills that take a little while to pick up and work out how to do that.

To your point, whether it is to a certain extent, taking the tools away. It feels like we've got to, to a certain extent, ignore the obvious productivity benefit and slow it down a little bit.

**Amy Laws**

Yeah, I guess it's the same when you train anybody junior in anything. Like, there is always a bit of a slowdown in speed for long-term gain, and I think it's the same kind of idea, just in a different setting.

**Colin Eberhardt**

It is – the problem is that in a simple sense, we're measured on two things: speed and quality. And more often than not, speed is the thing that is more visible than quality. And I think that's where we have to be very, very careful not to over-index on speed and forget about quality, 'cause I think that takes you down really down the wrong path.

**Amy Laws**

Yeah, I definitely agree with that. I think there's probably a bit of an ongoing question, as you said, quality and what is it gonna be like to maintain these code bases in 5, 10, 15 years' time. It's something that we just don't know at the minute.

**Colin Eberhardt**

Yeah. So Dean, from, from your perspective where do you think it's going and do you think perhaps some of the things that AI is less good at, at the moment it will potentially get better at, 'cause it, it feels like our role has shifted to, to hear how Amy sort of describes it, spending more time, 90% of your time working out how to describe the problem to the AI so that it is successful, and then maybe the last 10% is a little bit old fashioned. It's a bit more hands-on. How far do you think that's going to progress? Do you think AI will eventually be good at architecture? What? Where else will it start to consume our day jobs?

**Dean Kerr**

It's a million-dollar question, isn't it? It's funny, right? Because AI is extremely knowledgeable. It knows everything. It's been trained on everything, yet it still needs a little bit of a nudge and a bit of curation when it comes to things like architecture, where a lot of the time, perhaps it's making architectural decisions based on things it doesn't know that you might know.
It could be a future direction of the product, for example, or even just boiling down to a simple preference for how you think a library should scale for the end users. So, I'm not sure if AI would ever get to the point where it could get those sort of, uh, characteristics because the information just wouldn't be available to them, but I think they'd certainly get better at making a good guess at it.

**Colin Eberhardt**

You make an interesting point there. When you talked about architecture, you talked about scalability and uh, I think talking about libraries, you talked about the end user. You start moving into concerns that AI just doesn't have any of the inputs. It's, it's good at writing code because you can give it pretty much all the inputs it needs to be successful.

But even when you get to software architecture, that's not about looking down at the code, that's looking up at the business problem that, that this technology solves. And whilst AI's good at helping you sort of summarise Jira tickets and things like that. I haven't seen any evidence yet that it's good at discovering what a software product should actually do. I've not seen any evidence that it can do that yet. Which is reassuring.

**Dean Kerr**

Yes, for now. But yeah, that's, I guess why you went with fuzzy information and, and, uh, preferences. I guess it may have all the access to the code base and the data associated with the code base. It still can make some interesting abstractions sometimes that might make sense to it, but the abstractions might not be human-readable or as human-readable as well, which is a, another interesting characteristic that I could see probably improving in the near future there.

**Colin Eberhardt**

Yeah, it does feel like the limits are going to be at or close to the point where you need to get humans involved, whatever that might be. That feels like the area where AI will stop being useful. I guess to wrap up, and I think, one of the interesting things about AI is that it's changing the way that we approach software, but it's also having an impact on how people feel about software.

And I know Amy, when you went cold turkey, I guess lots of the things that you mentioned were, were generally quite negative, and some of them were just quite funny about how frustrating it was.

### Joy, Craft, and What AI Changes About Coding

**Colin Eberhardt**

But one of the things that you mentioned that I thought was really notable was that you had a sense of pride, or a bit more joy in actually handcrafting the solution.

It'd be great if you could speak more about that. Was it a bit more fun? I know reading issues was drudgery, but the code part. How did that feel?

**Amy Laws**

Yeah. So, one of the things that first attracted me, I guess, to coding was problem solving, and that kind of high you get when you've had a really hard challenge, and you spend quite a long time kind of in the code, and you finally get that test passing or get that feature working. And I think I forgot that that feeling is actually really great.

And when you've used AI to write your code, I guess I feel less ownership of it, even though it is still kind of my work, because I've not kind of handcrafted and carefully gone through like every line of code. That high just wasn't quite the same, and that was something that I didn't realise I missed.

So, a lot of the bugs that we had in this project were often quite hard to pin down, and it was a real challenge to kind of work out what was causing the issue. I think a lot of the time, when you worked it out, the solution was quite simple. But yeah, that really great feeling when you've finally fixed a really hard problem is something that first attracted me to this job, and I didn't realise that I'd kind of missed.

And as you said, like knowing that you have built something or you have solved the problem is something that I guess is going away a little bit as we're kind of more hands-off with the code.

**Colin Eberhardt**

Yeah, it's a really interesting sort of connection we have with the code that we write. I think a suitable analogy for people who have not written software is potentially carpentry. You can imagine that there's a great difference between, I don't know, building a chair or something like that and crafting it with your own hands, versus if you just programmed it into a computer and a CNC machine built it. I think that the end result is exactly the same, and it could be exactly the same human being that has achieved that end result.

But I think a lot of people would understand and relate to there being a greater sense of achievement through actually crafting it with a hand chisel than programming a machine to do it.

**Amy Laws**

Yeah, I think that's exactly right. And I think as software developers we do have a pride in the things we've built, and actually seeing people use them or knowing that people are using them is a really great feeling, and it's something that maybe is gonna change a little bit in the future.

**Colin Eberhardt**

Yeah, I agree. I mean, Dean, you've been doing software for a long time, and I'm assuming that a lot of the time you've been working on software, you've experienced that joy of creating an elegant solution or refactoring some code just because you felt it looked better, and that gave you joy.

What do you think about this shift in software engineering?

**Dean Kerr**

Yeah, it's interesting really 'cause as you say, it's, I guess, I've been in the business of the industry for over a decade. And I think things have moved slowly between that decade, I guess, as I gradually got more senior, moving slowly and more away from the code and getting my problem-solving thrills, maybe at a higher level than low-level code. But, I still got immense satisfaction out of fixing a bug that might have taken a long time or took a lot of analysis to get to the bottom of, or like you say, spending a good amount of time with maybe an initial solution that I refactored into a quite elegant one.

So, yeah, there's still the satisfaction there for that, but there's equally, you know, you get satisfaction in building applications and products as well. Um, I think I've gradually shifted to be sort of in the middle, from doing purely development work to being, you know, a product owner only.

So, I think that's a nice balance to have. But, I think, AI if it keeps progressing at this rate, I think you're gonna have less of that sort of lower-level working satisfaction and more of getting satisfaction and morale from solving higher-level or maybe even product-oriented problems going forward.

**Colin Eberhardt**

I guess taking the conversation full circle and coming back to The Experiment, do you feel any more satisfaction from The Experiment knowing that your pull request eventually got merged and the, and the software that was shipped?

**Dean Kerr**

I'd say that satisfaction is equal, whether I was handwriting every line or I reviewed it and it was effectively mine, I guess, to the same extent anyway. There's still that responsibility and ownership of a pull request, regardless of whether it was AI that generated the code for you in one prompt and it "one-shot" it, versus you handcrafting it over a week.

**Colin Eberhardt**

Yeah, so I guess it's time to put the ultimate question to each of you and see whether you are, you are happy to answer yes, no, or sit on the fence and go with a maybe. So Amy, do you think AI has taken the fun out of software development?

**Amy Laws**

I think I'm gonna have to go “maybe” on this one. I think I've definitely lost some of the areas that I used to have a lot of joy in, but as Dean said, you kind of find them in other areas, if that makes sense. So actually, I find AI absolutely fascinating and if I can get it to solve a really hard problem for me.

That brings me joy in the same way that fixing a really hard bug would. So yes, sorry to avoid the question, but I think it's just shifted where we find it.

**Colin Eberhardt**

Oh, on the fence then. Come on, Dean, can we get you to come off the fence, or are you gonna do the same?

**Dean Kerr**

Well, you know, rather than no, which is a bit of an absolute, I could say not yet if that's a good, yeah, second one, anyway. I think for me it's been really interesting to see all the knowledge I've built up in industry so far as a developer, how quickly I thought it's almost becoming obsolete.

I thought, you know, you'd learn a couple of languages, and maybe one or two of those languages would, you know, fall out of fashion, go out of date and not be as relevant any more. But for the whole development bit itself to potentially be obsolete is a bit sad. But, at the same time, I think I still get the same satisfaction, like you say, to getting a pull request merged or a particular tricky feature deployed, and seeing it used by users. So, I've put not yet rather than, no, because, uh, like I said, AI's changing from week to week. So, it might be no at the minute, uh, but it could, uh, yes later on as it progresses.

**Colin Eberhardt**

Yeah, I totally get what you mean about this; it does genuinely feel like we've reached quite a surprising point. I mean, I think a lot of us could see that this was going to be a big thing, you know, as far back as a couple of years ago, but I didn't think we would be reaching this particular point. So I guess it's, it's my turn and I, I'm gonna fall off the fence. I'm gonna say no, AI is not taking the fun outta software development, but I'm gonna come in with a caveat, that I think the place that you find fun has moved completely. It's not where it used to be. And I think that's the sort of critical thing.

And I sort of almost discovered this myself from looking at some of the hobby projects, 'cause you know, I don't write much code in the day job, but I still love writing code and building things. And I looked back, and four or five years ago, a lot of the stuff I was doing was with WebAssembly, and I was writing an emulator for an Atari 2600.

And the funny thing is. I never played a game on it. That wasn't the intention. I, I just wanted to build the thing, and that was it. Whereas now, the hobby projects I work on tend to be ones where it's a thing I actually want to use, and the apps themselves are really boring. You know, Crud style, form-based applications where the code itself would bore me stupid.

But, I'm having more fun actually building things that I actually use. So, for me personally, I still find it fun, but the things that I find fun have changed completely in the space of five years. Oh, I get the final say. Cool. Well, 'cause I'm the one that, that came off the fence.

### Episode outro

**Colin Eberhardt**

And that brings this episode to a close. While AI hasn't necessarily taken the fun out of software development, the change in our role and focus means that this fun is something we have to find somewhere else, and it may not be derived directly from the act of writing code. This is going to be an uncomfortable realisation for some people.

If you've enjoyed this episode, we'd really appreciate it if you could rate and review Beyond the Hype. It'll help other people tune out the noise and find something of value, just like our podcast aims to do. If you want to tap into more of our thinking on technology and design, head over to our blog at scottlogic.com forward slash blog.

So only remains for me to thank Amy and Dean for taking part, and you for listening. Join us again the next time as we go Beyond the Hype.