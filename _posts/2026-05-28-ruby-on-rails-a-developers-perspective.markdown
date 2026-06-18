---
title: Ruby on Rails - A Developer’s Perspective
date: 2026-05-28 00:00:00 Z
categories:
- Tech
tags:
- Technology
- Software Development
- Ruby on Rails
- Web Development
- Rapid Development
summary: I recently picked up Ruby on Rails for a client project, and it turned out
  to be a more enjoyable experience than I had expected.
author: mthomas
image: 
---

After more than five years building production systems with Java and working across a range of backend and cloud technologies, I’ve developed a healthy habit of approaching new frameworks with both curiosity and scepticism. That mindset guided me when I recently upskilled in Ruby on Rails for a potential client project — and the experience turned out to be more interesting than I’d anticipated.

## What Ruby on Rails Actually Is

Ruby on Rails (commonly just called Rails) is an open-source, server-side web application framework written in Ruby. It follows the Model–View–Controller (MVC) architectural pattern and is heavily opinionated in how applications should be structured. Its core design principles are:

- **Convention over Configuration**: Many decisions are made for you by default.

- **Don’t Repeat Yourself (DRY)**: Duplicate logic is actively discouraged.

- **Full‑stack by default**: The database layer, routing, controllers, views, background jobs, and testing tools are all integrated.

Rails was first released in 2004 and, despite regular claims of decline, remains actively maintained and widely used. In fact, what distinguishes Rails from many frameworks is not novelty, but maturity; its patterns have influenced frameworks across ecosystems, including Django (Python) and Laravel (PHP).

### Where Ruby on Rails Is Used Today

Rails is not a niche framework confined to hobby projects. It is used in production by companies operating at global scale, particularly where rapid feature development and stable long-term maintenance matter.

Notable organisations using Rails include: _GitHub,Shopify,Airbnb,Basecamp,Twitch_

As of March 2026, Rails 8 is the current major version, with continued investment in performance, security, and modern development practices. 

In today’s market, Rails is most commonly used for:

- _SaaS platforms_, especially MVPs that need to reach market quickly
- _Content-heavy applications_ with complex business logic
- _API-driven systems_, where Rails acts as a robust backend for mobile or JS-heavy frontends 
- _Internal platforms and tooling_, where maintainability and developer productivity outweigh raw throughput

Rails has also adapted well to modern infrastructure expectations — containerisation, background job processing, caching, and cloud-native deployments are all first-class concerns in current versions.

## My Journey

My experience with Ruby on Rails felt like a love–hate relationship.

At first, I was impressed but deeply sceptical. It felt almost too good to be true — models, controllers, and test files appearing instantly was undeniably satisfying. At the same time, it created a nagging sense that a lot was happening “behind the curtain”, with important details carefully hidden away by convention.

That initial discomfort didn’t take long to turn into frustration once the magic broke. When something behaved unexpectedly, the error messages didn’t always point back to code I had written. Instead, I found myself reverse-engineering framework behaviour, trying to understand decisions Rails had already made on my behalf rather than reasoning directly about my own logic.

Over time, though, that frustration softened into acceptance. Rails isn’t inherently problematic; it simply asks for a different kind of trust. You’re encouraged to lean into its conventions, slow down, and learn its way of doing things — even when that way feels opaque at first.

Despite the frustration, I realised that I was able to get a working solution up and running in a fraction of the time it would have taken to hand-code the same functionality elsewhere. Scaffolding and boilerplate were handled effortlessly, leaving me free to focus on the shape of the problem rather than the mechanics of wiring things together.

You can make rapid progress without fully understanding the underlying architecture or design patterns at play, which is both empowering and dangerous. That hidden depth only really reveals itself when you need to debug something subtle or push the framework beyond its happy path.

Getting started is easy — especially with the clear documentation — but stepping outside the rails (quite literally) can feel like pushing against the framework rather than collaborating with it. So while Rails is undeniably friendly to beginners, it can feel surprisingly opinionated to experienced developers. That tension is where most of my friction lived.

That tension is what makes Rails such a paradox — and, oddly, a delightful one.

### Key Insights

#### Generators
One of the most immediately striking aspects of Rails is how much productivity it unlocks through conventions and tooling. The framework’s generators, backed by Active Record (Rails' ORM), remove a significant amount of boilerplate.

For example, a single CLI command:

~~~~shell
generate model Product name:string
~~~~

creates a model, a corresponding test file, a database migration, schema updates, and the necessary directory if these do not already exist. It also lays the groundwork for standard CRUD operations. This level of automation can feel surprising at first, particularly coming from environments where each of these steps must be wired together manually.
It allowed features to be delivered quickly with minimal ceremony.

#### Associations and Data Modelling

Associations are where Rails feels particularly expressive. Relationships such as belongs_to, has_one, has_many, and has_many :through read almost declaratively.

Relational modelling can be expressed in a small amount of highly readable code:

~~~~ruby
class Product < ApplicationRecord
  belongs_to :user
  has_many :line_items
  has_one :profile, dependent: :destroy
  has_many :orders, through: :line_items
end
~~~~

Despite its simplicity, this definition establishes associations, infers foreign keys and generates migrations. SQL is abstracted away entirely unless you explicitly choose to drop down to it. The emphasis on convention means configuration becomes largely implicit, shifting focus away from setup and towards domain modelling.

Features such as 
`dependent: :destroy` stood out to me. It defines what happens to associated records when the parent record is deleted, allowing cascading behaviour.
In this example, deleting a product will automatically delete its associated profile, which is a common pattern that would otherwise require manual handling in many frameworks.

#### Rails Console and Debugging
Rails also provides a powerful interactive environment through the Rails console, which loads the full application context and database connection. It can be used to query, inspect, and manipulate application state in real time:

~~~~shell
Product.firstProduct.create(name: "Cupcake", stock: 12)
Product.last.destroy
~~~~

This eliminates the need for ad hoc scripts or temporary endpoints during development and debugging. The feedback loop is fast, direct, and tightly integrated with the application itself.

The documentation often emphasises logging and console-based inspection for debugging, which can feel limiting if you are used to IDE-driven debugging workflows. However, with the addition of VS Code Ruby and Rails debugging extensions, the experience becomes much more aligned with what developers expect from mature IDE tooling. Breakpoints, variable inspection, step-through debugging, and thread visibility are all available, with the added benefit of the Rails console running alongside the debugger.

### Comparing Spring and Rails

Working with Ruby on Rails felt both familiar and disorienting in equal measure. The high-level architectural concepts — MVC, layered responsibilities, and REST-centric design — are recognisable, but the way Rails guides you towards those outcomes is markedly different.

The most immediate difference was how much Rails removes up-front decision-making. As a Spring developer, I’m used to explicitly defining configuration, wiring dependencies, and making architectural intent visible through annotations and structure. Rails, by contrast, leans heavily into convention over configuration. Over time, though, it became clear that Rails isn’t removing complexity so much as delaying it until it’s actually needed.

Active Record was another notable shift. It plays a role similar to Hibernate or JPA in the Java ecosystem, but with far less visible configuration.
Compared to Hibernate/JPA, it’s far more opinionated and is tightly integrated into the framework. It’s designed to be simple and intuitive for common use cases, but it can feel restrictive when you need to do something unconventional. The trade-off is that you need to be disciplined in understanding what the framework is doing on your behalf — especially as data access patterns become more complex.
In contrast, Hibernate/JPA offers more flexibility at the cost of simplicity.

The framework, tooling, and ecosystem are optimised to get something working end to end quickly. Compared to Spring Boot, where robustness and explicit configuration reinforce enterprise safety, Rails prioritises momentum. For early-stage development or well-bounded domains, this feels like a genuine advantage rather than a shortcut.

| Aspect               | Ruby on Rails                 | Spring                                      |
|----------------------|-------------------------------|---------------------------------------------|
| ORM                  | ActiveRecord                  | Hibernate/JPA                               |
| Philosophy           | Convention over configuration | Heavy configuration, annotations everywhere |
| Developer experience | Fast prototyping              | Enterprise robustness                       |
| Ideal for            | Rapid CRUD apps               | Complex enterprise architectures            |

## Final Thoughts

Just as I was getting comfortable, the client project I’d been preparing for failed to materialise, and my short Rails experiment came to an abrupt end. I found myself back in familiar Java territory, my detour complete.

Whether I’ll return to Ruby on Rails one day, or whether it remains the framework that got away, I don’t know. But one thing I’ll leave you with is this:

Rails may not always be love at first sight, but it’s undeniably efficient. It feels like the older, wiser framework in the room — not flashy, not loud, probably not lining up to give a TED Talk to stay relevant — but still deeply competent. Quietly generating files, enforcing conventions, and occasionally making even the sceptics pause and think:

“Okay… that was actually pretty cool.”