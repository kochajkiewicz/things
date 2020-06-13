---
title: Is it a design system if you haven't written about it?
date: 2020-06-13T15:20:58.608Z
description: I'm building out a big bunch of styles and interface elements. I'm
  not done, not even close. Of course I'll write about it, wouldn't you?
---
Imagine two separate experiences – say, native mobile and web – for one product. Web leading the way, mobile playing catch-up. With a leaner feature set, a smaller user base and no legacy decisions hanging over it, this mobile experience is a playground for more focused product design, and evolved functional and perceptual patterns.

Now, imagine the process of retrofitting a mobile pattern into the web experience. It feels low effort, it's shortly before deployment and, for the purpose of this post, the form factor difference is irrelevant. It's a good idea and our customers' behaviour told us so.

I doubt this pattern would end up being archived as high fidelity pixels. I am not redrawing these rectangles unless it's with a sharpie.

A system that makes designers produce high-fidelity outputs for the sake of consistency with production is a hamster wheel. A system that prioritises consistency over evolution of approaches is probably too rigid for a small organisation with limited resources. **If it's not in production, it's not the source of truth**

- - -

We could down tools and count the instances of buttons. Or we could look at date pickers and wonder how the hell do we have 6 of them. Then, converge on the "new" official component to fulfil a given purpose and begin another cycle of pixel entropy.

I drew a primary and a secondary button and realised that – while their purpose made them look different – their low-level properties were in tune with properties of other elements of the interface. I defined a border colour as an `rgba` value and could use it again on a variety of elements to ensure visual consistency. But stopping there would be a wasted opportunity.

Once this value is defined – as `border-colour-strong`, perhaps? – I could treat its opacity as a point on an imaginary scale. Next, consider the `hsl` values of its colour and define how they change when an element was interacted with – forming a scale around `:hover`, `:active` and `:disabled` pseudo-classes and how an element might respond to those.

Documenting such relationships in a straightforward manner is a difficult task for today's interface design tools. Keeping the results in sync across multiple elements a lot less so, but still requiring curation. Using the underlying relationships successfully to our advantage is bound to be difficult if designers and engineers are forced to study existing pixel artefacts to find them. **Building scales and constraints rather than artefacts is design work**. Crafting yet another passive-aggressive message for #frontend-eng is not. 

- - -

Some design companies' marketing budgets elevated "design systems" as the number one thing to do – and designers followed. Systems became passion projects for some, strategic investments for others. I'm curious how many systems are treated as internal-use products rather than static libraries. How often has a design system project been a box-ticking dopamine binge rather than an exercise in researching and addressing the system users' needs?

Is the system adopted by multi-disciplinary product teams? If not, why not? Has the time spent on UI design and build dropped significantly since adopting the system? Have the core UX metrics of our product improved where the system has been in use? How should we measure consistency of the interface? How often has a component been modified or added and has in turn impacted those metrics? How can we tell if changes to rules or components are being propagated as efficiently as possible to other parts of the system? **Monitoring its performance is the difference between a design system being a passion project or a product**.

- - -

When things get hectic at work, I tend to think about drawing less and designing more, and automating away the repetitive parts of my job to focus on problems larger than a pixel.

Last thing I want to deal with on a busy day is a component I need to detach from its master instance for the umpteenth time just to make it work for a particular use case and somehow still fit into the front-end puzzle.

If at its lowest level, a system is composed of individual elements rather than their basic properties, small style changes can render the entire system brittle. If those elements are archived as static pixels and treated as a source of truth, implementing such changes comes with overheads harder to prioritise or justify.

None of the issues I'm grappling with are fully solved by today's design tools, if in that category we only include the likes of Sketch, Figma or Adobe XD. But the problems we face today, imperfect tooling and a maturing discipline inform the best practices of tomorrow. 

- - -

As Robin Rendle put it in his essay, [Systems, Mistakes, and the Sea](https://www.robinrendle.com/essays/systems-mistakes-and-the-sea): 

> The ugly truth is that design systems work is not easy. And what works for one company does not work for another. In most cases, copying the big tech company of the week will not make a design system better at all.

Dan Eden's "[Subatomic Design Systems](https://daneden.me/blog/2018/subatomic-design-systems)" is a great overview of how elements within a system are compositions of low-level properties, and how the consistency of the system largely depends on those properties.\
\
Finally, Alla Kholmatova's "[Design Systems](https://designsystemsbook.com/)" is an amazingly accessible and thorough guide to embarking on a design system project, chock-full of both theory and practice. Reading it once is definitely not enough.