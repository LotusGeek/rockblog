---
title: "Happy Coding! Crafting Context in AI-Assisted Development"
date: 2026-08-25
draft: false
tags: ["AI", "AI-Assisted Development", "Context Management", "Claude"]
categories: ["AI Best Practices"]
description: "A practical guide to managing AI context across sessions — persistent instructions, prompt strategy, documentation, and the planning process that keeps AI-assisted development from falling apart."
---

> [!NOTE]
>
> I'm not here to sell you a class, a framework, or a $500 prompt engineering course. I'm an elder IT geek with 35+ years of experience, working in R&D for a Really Big Company. Now I'm using AI to get more done in less time than I ever imagined possible even two years ago. This series is how I'm doing it. No spin, no pitch. Just real world advice.

The Internet is littered with AI development horror stories, where some Joe Schmo decides he's going to be a "developer" one day, sits down at his AI, and tells it to build him an app.

"Look ma, I'm coding!" --Joe Schmo

No Joe - no you're not. Your AI is confidently trying to please you like a digital puppy dog - but what it's building isn't going to be reliable or usable.

Successful AI-assisted development takes careful planning and understanding of what AI can do, what it does best, and what it sucks at. Once you understand these concepts, you can begin productive AI-assisted development. Here are some strategies I use.

In the [first article in my AI Best Practices series](https://www.rockyoliver.com/post/what-ai-is---article-02/) I gave you an overview of the strategies I use to get the most out of my AI driven development.  Now let's dive into some specifics.

## Wide vs Deep

When working on AI assisted projects, they typically fall into two categories:

- **Wide Projects** - these projects tend to be more task oriented, often with repetitive, predictable steps. A great example of these is preparing monthly and quarterly reports. The work performed to create these reports tends to be similarly shaped, while the data and target audience for each report may be different.
- **Deep Projects** - these are projects that are typically complex, require a great deal of planning, and are usually accomplished in a series of phases. Examples would include developing a collaboration platform or invoice tracking system with complex workflows.

Understanding the type of project you're developing will greatly influence the way you use AI to assist you in performing the work.

### Wide

Wide projects are really the "low hanging fruit" of AI work. AI is fantastic at well defined tasks with a predictable outcome. In fact, this is a great place to run multiple AI processes in parallel, each one handling a single report — instead of working through them one at a time. This is often called *agentic AI*, and it's worth knowing the term since you'll see it everywhere. The result? Reports that used to take hours or days to prepare now take minutes.

### Deep

Deep projects are the opposite. They require more planning up front, and usually play out over a series of iterative sessions stretched across days or weeks. This means you'll need to be very disciplined in how you work with your AI, because mistakes made here tend to compound. And if you're not on top of what your AI is creating, and don't put in the effort to keep your AI on task, it will happily carry on confidently creating a pile of broken code. 

This is where most of the "vibe coding" horror stories you've heard about come from. It's not because AI is "bad" at deep projects, it's because the developer didn't have a strategy for managing AI context, or they didn't actually understand what they needed to build - or both.

So let's talk about ways you can actually pull off deep development with AI, without feeling like Dr. Frankenstein.

## It's All About the Context

Let's begin by talking about some basics with AI. Now, I use Claude quite a bit; that doesn't mean it's the best, and everyone has their favorite AI (or AIs) they like to use. And while Claude has many flavors, I tend to use Claude Code (Anthropic's Claude version built specifically for development) for my work. For me and the work I do, Claude Code works well. So my discussions may be a little Claude Code-centric, but the underlying concepts apply across all AIs. 

Let's begin by discussing what we call a *session* in AI. A session is simply a conversation you're having with your AI client. Each session is "stateless", meaning it's unaware of previous conversations. This means every time you start a conversation with your AI it's almost like you're meeting it for the first time. It has no idea of what you've done, what you've learned, etc. even if you did all of that with the AI itself five minutes ago; in other words, it has no *context*.

"But Rocky, it remembers some things about me, and some general stuff about things we've done."

And you're right - which leads me into the tools AI uses to maintain various levels of *context* between conversations, beginning with **memory**.

### Context Begins with Memory

While sessions are generally stateless, some things do persist between sessions. All AIs have some concept of what we'll call "persistent instructions", and in a very general sense they tend to fall into three levels:

- <u>Basic Info</u> - many AIs will remember general things about a user - name, location, etc. - but this varies
- <u>Working Info</u> - this would be general rules across all sessions. Things like your preferences when dealing with GitHub, how you like to work (do you want to be challenged when something seems off, do you want terse or verbose responses, how do you like to structure your repos, naming conventions, etc.) 
- <u>Project Info</u> - this would be information specific to the current project or repo. This would include things like file locations, github repo names, other people working on the project, project-specific rules, etc. This also includes patterns the AI notices while working - recurring bugs you've flagged, build quirks, code style you've corrected the AI on, etc. Now this level can vary greatly between AIs, but many of them, especially those with a coding focus, have some version of this.

In Claude, you'll see these files mentioned as `MEMORY.md`, `CLAUDE.md`, etc.`CLAUDE.md` holds stuff I tell Claude to remember, and `MEMORY.md` holds things the AI notices, like the aforementioned recurring patterns. Claude typically manages the updating of these itself, but it can be fun to poke around in them to see exactly how it tracks this information.

One quick side note - you notice that a lot of the files mentioned have a `.md` extension. `.md` is the extension for *Markdown* - a plain-text formatting standard that's become the default way AI tools read and write these kinds of files. You'll see that extension a lot here (even this very article was written as a `.md` file).

Now let's talk about managing this contextual memory.

### Managing Context Across Sessions

Remember that each AI session is essentually "stateless", meaning it doesn't maintain detailed context between each session. So while it may have some general sense of the project based on the persistent instructions, a new session woin't remember what was just discussed in a previous session. This means you have to have a plan for maintaining context state between sessions so you have some continuity.

I use a three-tier model for managing state across sessions:

- Persistent Instructions - this is the basic information that's largely managed by your AI across sessions that we just discussed
- Meaningful Prompts - this is the initial instructions you give a new session to let the AI know what's going on, background information about the project, and what you hope to accomplish in this session
- Documentation - these are documents created as work product from one or more sessions; think of them as a reference library for information about the project

The trick is managing all three of these in a balancing act so that you and your AI can be as productive as possible in the most efficient manner as possible. With this in mind, let's talk a bit more about strategy.

#### Session Sizing

You know how when you're working on a complex problem, there's only so much you can hold in your head before you get confused? So, you might start writing some stuff down so you don't have to keep it all in your head at the same time, which frees up your mind so you can think more clearly about the problem. Well, AI sessions work in a very similar way.

Every time you give a prompt for a session your AI loads all of that context and information into memory, and as it works through the problem it has to keep up with an ever increasing load of information - it's putting more and more balls into the air. This means that the longer and more complex a session is, the quality of the session's output will begin to degrade. The AI will forget things, lose track of the bigger picture, or in the worst case it will confidently hallucinate and produce work product that is absolute crap.

Therefore it is better to break down the steps to accomplishing your goal into very small, discrete, focused tasks. Remember the old riddle: how do you eat an elephant? While it's possible to force your AI to eat your elephant-sized project in one bite, it's much more likely to be successful if you let the AI eat the elephant one bite at a time.

Now a lot of effective AI development strategy depends on how you plan and design your project before you and your AI write the first line of code; however, that topic warrants its own section, which we'll discuss later. For now, let's talk about how you can keep your AI consistently on the same page from session to session.

#### Threading Context Through Sessions

If you're going to be working through a project in a series of small, discrete sessions, you'll need some strategies for maintaining the context between those focused sessions. Doing this requires a three-tier balancing act - managing your *Persistent Instructions*, crafting *Meaningful Prompts*, and creating relevant *Documentation*.

##### Managing Persistent Instructions

This is the place where you should establish your ground rules for how you want your AI to work on your project. Here are the three legs of what I call the Accuracy Stool, that I establish with every project:

- <u>Never Assume</u> - AI often wants to make assumptions because it appears it's working faster, but when it comes to development, it's never a good idea to assume. Make sure your AI knows that it should take the time to verify anything it might otherwise assume.
- <u>Measure Twice, Cut Once</u> - this is a natural follow-up from the Never Assume rule - double check everything before you actually write or change code. This is especially important if your project is a part of a larger, interdependent effort. If you think some other service or function is available for your use, then verify it before writing in the dependency.
- <u>Ambiguity is the Bane of Development</u> - the third leg of our Accuracy Stool. Quite often AI will guess about something and gleefully press forward based on that guess. Just like there's no crying in baseball, there's no guessing in development. If something is ambiguous, whether it's input from other areas or projects, or your own instructions to your AI, then make sure your AI knows that it is responsible for clarifying that ambiguity.

One thing that will happen as a project progresses, especially a larger project with a lot of moving parts, is that the various Persistent Instructions files (e.g. `CLAUDE.md`, `MEMORY.md`, etc.) can get big and unwieldy. Often AIs put a limit on the size of these files, and overall it's good to keep them lean, current, and focused on the state of the project. Therefore I've come up with a strategy I call the "Memory Archive". Basically I instruct my AI to set up a `MEMORY-ARCHIVE.md` file, and offload things that might be worth keeping for reference, but aren't relevant to the work currently taking place. And during our context maintenance process (more on that in a bit) I have my AI periodically review what's in the `MEMORY-ARCHIVE.md` file and remove anything no longer needed. This way I can keep the current memory context as lean and focused as possible without losing anything that might be needed for reference at a later date.

##### Creating Meaningful Prompts

You should always begin your sessions with a prompt that "sets the stage" for the task you're about to do. This prompt should include pointers to documentation and reference files needed for the task, TO-DO lists, and a brief description of the current task at hand. It should also clearly state the goal of that particular session. This will greatly enhance the productivity of your next AI development session.

One trick I use is something I call *Prompt Stringing*. Prompt Stringing is basically having the current session craft the prompt for the next session. Since the current session has all the context already loaded about the state of the project, the task just completed, and what needs to be done next, it is best suited to write the prompt for the next session. You should concisely communicate exactly what you want to accomplish in the next session, and ask the AI to craft the prompt so that it's most efficient for AI digestion, not for human consumption. This will greatly cut down on superfluous language that it would normally include to make it human readable - and this in turn will save context and tokens.

##### Creating Relevant Documentation

Now not every aspect and detail about a project needs to be loaded into the current session's context memory. The current session context should only include the information needed to complete the current task at hand successfully. But your AI may also need some documentation available for reference as needed - think of your documentation as a reference library of sorts. This should include documentation on the overall plan, architecture of your project, organization of the code, possibly relevant technologies being used, and detailed design specs. Since creating this corpus of docs is so important, we'll address this in more detail later.

Now that we've discussed the structure of how we maintain proper context across sessions, let's talk about keeping all that contextual information current and focused.

#### Context Maintenance

As projects progress they inevitably evolve - and during that evolution new things are discovered, some things become irrelevant, and some things become outdated. Most projects, especially AI-assisted development projects, move very quickly - and as such the body of information evolves as well. Therefore it's necessary to become pretty disciplined at periodically auditing and scrubbing all of the documentation and metadata surrounding a project.

Most of my projects consist of an overall development plan and TO-DO list, and then each item on that TO-DO list is completed in a series of smaller focused task development sessions as we've discussed. Whenever I finish a TO-DO item, I then do a Context Audit & Cleanup. Basically, I ask my AI to take a forensic look at ALL of the context and metadata generated during the project since its inception. I remind my AI that nothing is to be assumed, everything is to be verified, including architecture, references, callouts, links, and so on. Everything should be evaluated critically, inaccuracies should be corrected, stale information should be removed, and things should be archived or deleted outright where necessary.

Now let's talk about the part of this that is probably the most important, and which depends largely upon you - planning and documentation.

## Planning and Documentation

A lot of the problems people have with "vibe coding" are that the user often doesn't know what they actually want or need, and they just throw a half-assed prompt at their AI and hope for the best. And given the problems we've been discussing with AI context, sessions being stateless, etc., those "seat of the pants" vibe coding sessions usually result in half-assed code.

Like most things in life, you can avoid a lot of problems by careful planning up front. Take the time to work out exactly what you're building - its shape, feature set, architecture, target audience, and so on. Then have a plan for how you're going to actually execute the project. Here's how I would design and plan a typical project before I write the first line of code.

### Setting the Stage

Just like each session prompt sets the stage for that session, your first prompt of your project should set the stage for what you're about to undertake. You need to provide the lay of the land and ground rules to the AI, to establish the initial context and scope of this effort. The first prompt should contain things like:

- Initial Purpose and Goal - What do you want to have at the end of the effort? The work you do to build a proof-of-concept is vastly different from the work you do to build a shipping product, so it's good to understand the "shape" of what you're building.
- Relevant Stakeholders and Users - Sometimes stakeholders and/or users may have conditions that warrant added weight to their desires or input. It's good to not only know who's involved and interested, but *why*.
- Initial Design Ideas - You've already been thinking about this project, maybe the initial structure or organization of functionality and data, and so on. AIs are great at reacting to things vs inventing things from whole cloth, so the more context or insight you can provide into your concepts about the project, the better.
- Predetermined Tech Commitments - Sometimes you have technology constraints - maybe your customer is already committed to a particular platform (e.g. AWS, Google), or maybe they already have a depth of in-house knowledge about particular languages (e.g. Python, Rust, JavaScript with React). These should be considered during the earliest phases of design.
- Predetermined Timeline - Often a project needs to be completed by a certain date. Knowing what that date is helps properly size the project so that it can be completed within the given timeline.

You should also use this initial prompt to establish the ground rules, like the Accuracy Stool we mentioned earlier. Things like:

- Don't Try to Please Me - The focus of your work with your AI should be to build the best project possible. You can't do this if your AI is constantly in the "puppy dog" mode. Instead tell it up front that you expect it to challenge you where warranted, with the goal of making the best app possible.
- Build It Right Not Fast - I want to build the right thing, and don't want to take shortcuts if it isn't the right thing to do. Quality trumps speed.
- Measure Twice Cut Once - Always double check design decisions, think about secondary and tertiary effects, blast radius, and so on.
- Ambiguity is the Bane of Development - Do not guess, do not assume. It's cheap to verify an assumption. If we have the power to check on something to determine accuracy, we should.

These are just some examples - you may do more or less, as your needs dictate.

It's also a good idea to let the AI know the direction you're heading for future sessions. Tell it explicitly that you're going to begin by doing a series of design sessions to get a solid development plan and architecture in place, and then you'll start development.

Now that the ground rules are established, let's dive into the design and architecture.

### Design and Architecture

The Design and Architecture phase of the project is arguably the most important phase of the whole effort. Everything moving forward from this phase will be based on the work done here. Therefore it's better to spend a few extra minutes here getting something right, rather than spending hours later trying to correct some fundamental design flaw missed during this phase.

This is the first phase where we're actually going to be producing some usable work product based on our efforts. Here are some typical artifacts that I generate during this phase, but of course I encourage you to adjust this list as your needs dictate.

- Executive Summary - Basically this is the elevator pitch for your project. Introduces the project, describes its purpose and goal, benefits, etc. Generally good to have, because you'll get asked about your project more than you anticipate.
- Architecture - This is a high-level architecture doc that explains how your features and data are organized, how they interact, and so on.
- Timeline/Phases - This is an overall high-level timeline on when certain milestones will be hit. Depending on the size of the project, this may be broken down into phases.
- TO-DO Lists - Usually the first one or two are pretty detailed, with later ones getting more fleshed out as the project progresses.

It's generally a good idea to have measurable goals for each step of your project, especially the items listed on the Timeline and TO-DO lists. It's hard to measure progress if you don't know what you're measuring.

One thing I want to make clear - ALL of these documents we're generating are to be considered "works in progress". While they are a roadmap for the project, they are not a religious tome - they are not infallible. This means that as you work through the project you may come across a finding that forces a fundamental change in design. That's fine, it's better to catch it now and take the time to do it right than do it wrong and fast and "hope for the best", because the best you can hope for is crappy.

Once you have a clean, comprehensive design and timeline in place, you're ready to start development; but before you begin, there's one more thing you should do.

### Adversarial Review

You and your AI have put in the work to design something worth building, and you're happy with it. That's great - but to be extra sure you didn't miss anything, it's always good to do one final pass, known as the Adversarial Review.

Basically you want to review everything you've generated with a fresh set of eyes - eyes focused on finding the chinks in your armor and flaws in your design. Now you can either do this in a fresh session of your current AI, or you can even use a different AI for the review. In VS Code I have both Claude Code and ChatGPT, and while I used Claude Code for the bulk of my development, I use ChatGPT as my adversarial reviewer - my own personal Spanish Inquisition (NOBODY EXPECTS THE SPANISH INQUISITION!! - Sorry, Monty Python references are known to surface on occasion 😉)

Remember, when creating the prompt for this Adversarial Review, you want to give the AI enough context to understand what's going on with the project, and what the goal of this session is - to give a critical, forensic review of the architecture and design and make sure it's as good as possible. Therefore I usually give it the Executive Summary we created earlier, I give it the location of the repository and the documentation, and I tell it that I want a forensic adversarial review of the project, design, and architecture. I also tell it that I want the findings it generates to be captured in a document called `ADVERSARIAL_REVIEW.md`. I also make sure it understands that if it has any questions, to please ask (you'd be surprised how often you need to tell the AI that).

Once the process is completed and I have my `ADVERSARIAL_REVIEW.md`, I go back into my development AI and start a new session with my intro context prompt and this document, and tell it to review these findings and we discuss the suggested changes. Then I just go through the iterative process of triaging these findings and updating my design.

Once this pass is done, I'm ready to begin development!

## Next Stop: Happy Coding!

Now you have some real world advice for starting your AI-assisted development journey. The suggestions outlined here aren't a part of some grand AI development methodology or marketing BS - they're simple, real-world strategies and techniques that have proven useful for this Elder IT Geek to get the most out of his AI development efforts. What you do with these suggestions is up to you.

Until next time - happy coding!
