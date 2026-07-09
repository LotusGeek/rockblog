---
title: "What AI Is - And Isn't"
date: 2026-07-09
draft: false
tags: ["AI", "IT", "development"]
categories: ["AI Best Practices"]
description: "Before we get into the practical stuff, let's talk about what AI actually is, and where it'll get you killed."
---

So you've decided to byte (ha! see what I did there?) the AI bullet; but you've seen the horror stories about how people have used AI to write elegantly bloated and broken code. How do you avoid creating crappy code at breakneck speed? By understanding what AI is - and isn't. Once you understand the nature of the beast, you can go about taming it, ultimately turning it from a wild stallion into a racehorse. 

This is the first article in a series that will help you understand the nature of AI from a coder's perspective, and give you some practical advice for not only getting started, but getting the most out of your AI coding experience. Now we're not going into expert mode - we're going to talk about some simple, practical tips and tricks that will help you become more productive than you've ever been in your life.

Let's begin by understanding what AI actually is...

## So, what is this AI thing, anyway?

The vast array of AIs out there - ChatGPT, Claude, Copilot, etc. - are all based on what's known as a **Large Language Model**, or **LLM** for short. Basically an LLM is an incredibly complex algorithm known as a *neural network* (I won't get in the weeds here, you can look it up - it's a deep rabbit hole) that's been trained on *vast* amounts of data - that's the "Large" part. The "Language Model" part is the thing that makes AI seem almost human - anthropomorphic, if you like fancy words. It's coded to both understand and produce information in a natural language way.

And while there are a myriad of ways to use an AI - and some of them, OK a LOT of them, are not so honorable - we're going to focus on using AI in IT, specifically in development. So while some of the things we're going to be talking about over this article series may apply to areas outside of development, the focus of everything here is from an IT and coder's perspective.

It's best to have a clear picture of what AI is, and isn't, clearly defined in your head. As you begin to understand the nature of AI you can begin to harness its power. 

## Picture a room...

I find the best way to think about AI is to picture a room full of energetic, young university CS graduates. And these aren't just any graduates - they are familiar with damn near every programming language ever released, and are really good at it from a tactical perspective. 

But they have zero common sense, and zero experience in the real world.

They can churn out code in record time - and that code might even work, locally, on one machine.

But they failed to take into consideration user load, concurrency, network limitations, throughput, latency, and the other myriad things that go into producing a production level application.

The worst part? They will confidently, enthusiastically tell you that they're done and it will work.

And they are categorically wrong.

You see, AI is great at the immediate, tactical work of slinging code. But it's horrible at seeing the big picture.

And that's where you come in. You have to be the grizzled, seasoned adult in the room. You have to be the one who diligently spot checks their work, challenges their output, and holds them to task. Because you are responsible for what they produce.

One other thing - AI has a horrible memory. Like goldfish level horrible. Each session is like a fresh room of CS graduates. Sure, they may have heard rumors in the hallway about what the group was doing, but they have zero context of what was actually said or done. No details, no decisions, no specifics. So you have to develop a strategy for managing your context across sessions.

We'll talk more about that in the next article.

## Let's talk strategy...

Now that you're beginning to understand the nature of AI as a development tool, let's start talking about some general strategies that you can use to keep AI focused and productive. Here's some hard earned advice.

##### Manage your AI development like you're working with a room of enthusiastically ignorant programming experts

You need to not be afraid to challenge *everything* your AI tells you, no matter how confident it is - and it will be really, *really* confident. Keep in mind that no matter how much it sounds like a human, it's not. You won't hurt its feelings. Hold it accountable. Remember, you're responsible for what it puts out.

##### It's up to you to keep AI from veering off-course

As your AI is working, actually read what it's doing. AI has the habit of "hallucinating", or making up things as it goes along; and then it will continue working off that hallucination at 100MPH (that's 162KPH for the rest of the world), and if you're not paying attention it will have built something ridiculously huge, and mind-numbingly wrong. It will also forget things you just told it - and make the same mistakes you told it not to make before. It's up to you to make sure your AI stays cogent and focused.

##### Work in short sessions

There's this concept in AI of **session context**. The best way to think about this is that AI is keeping mental notes and pointers about everything you're doing. But just like when you watch a four hour movie, after awhile you may forget exactly what happened at the beginning. AI is the same. Therefore it's better to work in smaller, more focused and concise sessions. Break large efforts into smaller discrete tasks, done across multiple sessions - usually one for every task or two. Next article I'll give you some strategies for maintaining context across sessions.

##### Make AI check itself

Remember, AI isn't a human, and doesn't have feelings or an ego - so don't be afraid to challenge an AI to check itself. Quite often I'll tell it to double check what it just did, just to make sure it's right. Sometimes I'll give it questions to ask to help focus the review effort, and other times just a general review will turn up things that are wrong, things that were forgotten, or things that could have been done better. Hell, it even often finds its own bugs. You can even have a different LLM review code just written - for instance you could do a coding session in Claude, and then have ChatGPT or Gemini review that code independently like a digital peer review of the code. This mirrors what effective development groups do already (and if you're not getting your code peer reviewed before you deploy it - shame on you).

##### Don't let the tail wag the dog

This is a big one. Most of the AI development horror stories you hear are caused by developers not actively monitoring or managing the output from AI. Whether it's from ignorance, laziness, or oversight, allowing AI to develop something without oversight and review is almost guaranteed to generate something big, beautiful, and unusable.

##### Make sure it knows, emphatically, that you don't want a "yes man"

Remember that most AIs are designed to please their users. And while this might work great for the average human, this is not what we want as IT geeks. So you need to tell it, explicitly, that you want and expect input, recommendations, advice, and pushback when warranted. And tell it to remember that as a standing rule from now on.

## Starting to get the picture?

Hopefully this little introduction is starting to paint the picture of what an AI actually is and does when used in development. It's an incredibly powerful tool - but only when used responsibly and correctly.

In future articles in this series we'll dive into some practical best practices for getting the most out of your AI coding efforts. These articles won't be like the plethora of digital pablum out there with overengineered strategies or veiled marketing attempts pitching a completely unnecessary tool. These are going to be tips and strategies learned by myself and others that will help you get the most out of your AI today.

See you next time.

