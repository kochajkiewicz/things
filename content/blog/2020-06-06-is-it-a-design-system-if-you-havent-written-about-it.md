---
title: Is it a design system if you haven't written about it?
date: 2020-06-13T17:38:25.591Z
description: Indeed, ,much has been written. This is not another piece of
  sponsored blog content about interface audits, though.
---


Halfway through the excellent "[Design systems](https://designsystemsbook.com/)" by Alla Kholmatova I stumbled upon "[Systems, Mistakes, and the Sea](https://www.robinrendle.com/essays/systems-mistakes-and-the-sea)", an exceptional essay from Robin Rendle. 

Alla's book is a captivating introduction to design systems and all that they encompass. Robin's essay is a real-life account of how difficult it really is to build an effective system.

Both the book and the essay got me thinking about all the approaches to systems I've been exposed to: talks, articles, documentation, conversations with colleagues and peers in the industry.

I am in awe of the number of articles, videos and webinars on the topic. I'm also grateful for all the knowledge that's available out there – but I feel that in our effort to systematise, we tend to focus on the components and completion of the system, rather than designing its constraints and behaviour around it. 

Not digging into the "why" behind the constraints we set for the system will impede scaling it. Not thinking about scaling it means its effectiveness will plummet as more elements are created and rules we've set become blurry. Not measuring its effectiveness makes a system a designers' passion project, rather than an internal product.

Here are three rules I'm keeping in mind as I build my first system.

## Rule 1: If it's not in production, it's not a source of truth

Imagine two separate experiences – say, native mobile and web – for one product. Web leading the way, mobile playing catch-up. With a leaner feature set, a smaller user base and no legacy decisions hanging over it, this mobile experience is a playground for more focused product design, and evolved functional and perceptual patterns.

Now, imagine the process of retrofitting a mobile pattern into the web experience. It feels low effort, it's shortly before deployment and, for the purpose of this post, the form factor difference is irrelevant. It's a good idea and our customers' behaviour told us so.

I doubt this pattern would end up being archived as high fidelity pixels. I am not redrawing these rectangles unless it's with a sharpie and takes a minute.

A system that makes designers produce high-fidelity outputs for the sake of consistency with production is a hamster wheel.

A system that prioritises consistency over evolution of approaches is probably too rigid for a small organisation with very limited resources.

## Rule 2: Use scales and restrictions

We could down tools and count the instances of buttons. Or we could look at date pickers and wonder how the hell do we have 6 of them. Then, converge on the "new" official component to fulfil a given purpose and begin another cycle of pixel entropy.

Dan Eden's "[Subatomic Design Systems](https://daneden.me/blog/2018/subatomic-design-systems)" is an excellent introduction to how elements within a system are compositions of low-level properties, and how the consistency of the system largely depends on those properties.

How does that work in practice?

As Dan breaks it down in his blog post, a button is a combination of a Label and a View – each of those being compositions of low-level properties.

Drawing a primary and a secondary button, I realised that while their purpose made them look different, their low-level properties were in tune with properties of other elements of the interface. I defined a border colour as an `rgba` value and could use it on a variety of elements to ensure visual consistency. But stopping there would be a wasted opportunity!

Once this value is defined – as `border-colour-strong`, perhaps? – I could treat its opacity as a point on an imaginary scale. Next, consider the `hsl` values of that colour and define how they change when an element was interacted with – forming rules around `:hover`, `:active` and `:disabled` pseudo-classes.

Documenting such relationships in a straightforward manner is a difficult task for today's interface design tools. Keeping the resulting values in sync a lot less so, but still requiring curation. Using the underlying relationships successfully to our advantage is bound to be difficult if designers and engineers are forced to study existing pixel artefacts to find them.

However, building out key-value pairs**\*** for our properties makes it much easier to map out those relationships, tie them to preferred scales and use values with intent, creating consistent interface elements and, eventually, experiences.

## Rule 3: But does it work?

The jolt of dopamine we get from completing a task motivates us to continue working, riding the wave of productivity.

Stability and security fall under our basic needs as human beings. Our infatuation with patterns, and uncanny abilities when it comes to spotting them comes from our ancestors' survival strategies.

Certain design companies' marketing budgets elevated "design systems" as the number one thing to do – and designers followed. Systems became passion projects for some, strategic investments for others. I'm curious how many systems are treated as internal-use products rather than static libraries. How often has a design system project been a dopamine binge rather than an exercise in researching and addressing the system users' needs?

Is the system adopted by multi-disciplinary product teams? If not, why not? Has the time spent on UI design and build dropped significantly since adopting the system? Have the core UX metrics of our product improved where the system has been in use? How should we measure consistency of the interface? How often has a component been modified or added and has in turn impacted those metrics? How can we tell if changes to rules or components are being propagated as efficiently as possible to other parts of the system?

As I continue to contribute to a system that treats production code as the source of truth and focuses on its ability to scale and adapt to needs rather than the perfect consistency of individual elements, I realise monitoring performance is a task that differentiates a passion project from a product.

A system that measures success by its coverage isn't doing much more than enforcing consistency. If at its lowest level sit individual elements, rather than their basic properties, stylistic changes can render the system  brittle. If those elements are archived as static pixels and treated as a source of truth, implementing such changes comes with overheads not every organisation is willing to prioritise.

## How's it going?

When things get hectic at work, I tend to think about drawing less and designing more, and automating away the repetitive parts of my job to focus on solving problems.

Last thing I want to deal with is a component I need to detach from its master instance for the nth time just to make it work for a particular use case and somehow still fit into the front-end puzzle.

As Robin mentions in his essay: "The ugly truth is that design systems work is not easy. And what works for one company does not work for another", I'm trying to set rules that will work for my team and a system that caters to our needs, at this point in time. 

All of the issues I listed above are commonplace when designing software products. None of them are fully solved by today's design tools. But the issues we face today when dealing with imperfect tooling and a slowly-maturing discipline inform the best practices of tomorrow. 

In the spirit of his article, and as my journey is only beginning, I'll make sure to share the good, the bad and the ugly of building that system.

**\*** (Yes, I'm aware I might have just described how design tokens work. It's a trendy and somewhat loaded term that I'd like to understand a little bit better before using it in a blog post.)