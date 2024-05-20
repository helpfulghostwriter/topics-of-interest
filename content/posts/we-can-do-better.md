+++
title = 'We can do better'
date = 2024-04-15T21:19:36+01:00
draft = false
+++

## Introduction
I've been toying with writing this for the past year, I'm still not sure if it's a good idea - like so much of my professional life recently I am hit with a degree of apathy.  Why am I writing this? Who is it for? Will it make a difference?

As I sit here rewriting this paragraph for the umpteenth time I think the answers to those question are:
1. Because I couldn't sit idly by without sharing my experience and ideas for others to hear and hopefully learn from.
1. It's primarily for me.  I'm writing this to organise my thoughts.  To see if they make sense.  To see if they resonate with anyone else. But it's also for anyone working in the public sector in IT (or Tech as we now seem to call it).
1. I certainly hope this will make a difference... to someone... some day... I put the odds somewhere in region of winning the lottery. But you've got to be in it to win it!

I'll probably spend a bit more time thinking about the answers to these questions later.  For now they're good enough.

Not for a moment do I think I'm the first person to have these thoughts.  Nor do I think some of what I'll propose is particularly original.

I think it's worth stating that I've spent almost all of my career working in the private sector - from large multi-nationals to startups.  I came to loathe the culture that capitalism breeds... but working in the public sector has given me an appreciation for that method of business which I never thought possible.

I don't know how many of these I'll write, or how quickly I'll write them.  But

## A quick disclaimer
I like to describe problems by referring to the experiences I've had. Sometimes I may come across as rude, arrogant or perhaps even a bit of a dick - I'm OK with this for a few reasons:
1. To change the status quo you quite often have to put people outside their comfort zone (yourself included!)
1. I'm not doing this to make friends.
1. I think most of the people I work with enjoy the experience (I'm aware that referring to working with me as an "experience" is borderline arrogant ¯\\\_(ツ)\_/¯)

I know numerous people that currently work, or previously worked, for public sector organisations. I have spent countless hours, days even, in cathartic discussions to the point where I'm convinced my experiences are not uncommon.

A lot of these problems aren't unique to public sector organisations.  But whereas private sector organisations cease to exist if they don't get on top of them, or at the very least minimise their impact, public sector organisation continue to absorb taxpayers money.

## Defintion of terms
Before we go any further I want to make sure it's understood what I'm talking about:
- **Private Sector Organisations**: refers to any business owned by an individual or a group. A private sector company sells goods or services to fund its operations.  Any surplus capital can be reinvested or distributed as profits.
- **Public Sector Organisations**: refer to any business or organisation owned by the government.  A public sector company provides goods and services for the benefit of its citizens. They are funded by taxes.

## So what is the problem?
In simple terms... <u>**it is hard to get shit done!**</u>

The following scenarios are designed to summarise my experiences of what it's like to work in the public sector.  Like I said before, I'm not saying none of this happens in the private sector, it's just this seems to be the norm in the public sector.

### Scenario 1: Le standup
You log in, just in time for your 09:30 "standup".  You make small-talk with those team members whose professionalism compelled them to join the meeting on time. Finally, at 09:35 you decide, _"let's crack on, I guess Joe isn't going to make it today..."_.  The "standup" commences, a time to recount what progress you made yesterday, what progress you think you're going to make today and whether you're blocked by anything:

> **Developer 1**: _"So I started on JIRA-123, but I couldn't do much because my WiFi was playing up.  I'm going to take a look at it today"_.  
> **Scrum Master**: _"OK thanks Developer 1.  Are you blocked with anything?"_  
> **Developer 1**: _"No I don't think so..."_  
>  
> **Developer 2**: _"I picked up JIRA-234. I couldn't get it to work, so I rewrote a load of the codebase until it did work.  I've submitted a pull request but it's a big one so maybe I can talk everyone through it?"_  
> **Scrum Master**: _"Great, thanks Developer 2.  Is anyone free to review the pull request?"_  
> **Someone**: _"How many lines of code did you change?"_  
> **Developer 2**: _"Around 2000"_  
> **Rest of the team**: _"tumbleweed"_  
>  
> **Developer 3**: _"I'm still working on JIRA-345, but I didn't like the way our linter worked so I spent most of yesterday implementing a new one locally and in CI."_  
>  
> **Scrum Master** _(In a smug, proud tone)_: _"That's Agile done for another day!"_  

### Scenario 2: Decisions, decisions
A new requirement has come in for a product your're responsible for.  As the Tech Lead, you need to reflect how this requirement will change the architecture for the product (let's just assume it does!). You clone a Design Authority document template which you need to populate with the details of what you're doing and why - because without approval from the "decision makers" you've got no hope of releasing to production.

The template has ~30 headings.  Somewhere in the region of 45 table rows that you have to populate.  Here's a few examples of the type of information being asked for before you'll be allowed to deliver the customers requirements:

> - Can this product be load balanced? is it scalable?  
> - Where will the build artifacts be stored?
> - Where is the code repository?

You've put together the document. Slaved over it for a couple of weeks, finding out all the information that has been asked for. You meticulously drew out all the components using draw.io because the document requires a low level architecture diagram. Your propsal is submitted and planned for review at the next Design Authority meeting.  The day arrives, you've made a note of a question you wanted to ask because you weren't sure whether to use SQS or Amazon MQ to handle a specific type of message.

The meeting begins.  At first there's about 5 people on the call. Within a few minutes this number has crept up to 10... then 15... 20... 40... gulp.  The meeting chair suggests we begin - Microsoft Teams shows 60+ pariticpants on the call. You talk through the changes and why they're required, eventually reaching an appropriate time to ask your question:

> **You**: _"I wanted to ask for your opinion on whether to us SQS or Amazon MQ as the middleware system for this change because I've not used Amazon MQ before."_  
> **Random Architect**: _"The Design Authority doesn't usually answer those sorts of low level questions."_  
> **You**: _"Oh OK sorry, are there any questions on the propsal?"_  
> **Random Architect**: _"I noticed you're using ECS Fargate, why aren't you using Lambda Functions?"_  
> **You**: _"Because the develoeprs are more comfortable using ECS"_  
> **Random Architect**: _"But we're a serverless organisation, you need to use Lambda"_  

In your mind you're thinking through the paradox: _"you didn't care about the technology choice when I asked you a question on the middleware tech, but you care whether I'm using ECS Fargate or Lambda?!?"_.  The rest of the meeting proceeds to be just as insightful:

> **Random Architect 1**: _"Are you using VPC endpoints to communicate with private services?"_  
> **Random Architect 2**: _"Are you encrypting your data at rest?"_  
> **Random Architect 3**: _"Did you know that AWS just released a new service that has a tenuous link to this topic of conversation?"_

If you're asking yourself why I labelled the Architects in the conversation as "Random", it's because they have no knowledge of what the product is, what the requirement is, or indeed what the customer wants.  As a result, their questions are little better than what you might get from a random IT Architecture question generator (although the generator would correctly classify Fargate as a serverless service).

### Scenario 3: Prioritise or parallelise?
Our senior leaders have have decided to set the business priorities for the next financial year.  Last year they had 20 priorities.  The feedback from most of the business was that they didn't have the resources to do everything.  Being the good leaders that they are they decided to listen to the feedback:

> _"We heard you. So this year we spent our away day being as rigorous as we could to make sure we have a clear set of priorities."_  

There's no prize for guessing that the _"clear set of priorities"_ was indeed clear, but there were still just as many.  What's more they've had the genius idea to tender some of the objectives to market - i.e. pay another company to parallelise delivery (which rarely delivers the results you had envisaged).

Day 1 of "operation paralellogram":  
> Consultant: _"Hi, I've picked up JIRA-456. But I'm not sure I fully understand what is required"_  
> Permie: _"OK I can help a bit, but I've got my own job to do. Can the delivery manager help?"_  
> Consultant: _"Oh... The delivery manager said to ask you because you're were overseeing this project from a technical perspective"_  
> Permie: _"-\_-"_

Day 60... (59 days of letting the consultancy get on with it)
> Consultant: _"OK we've got most of it working. As per the Statement of Work we're only allowed to fix bugs now"_  
> Permie: _"Wait a minute... you've used a completely different CI tool to our standard... how are we going to deploy this to prod?!?!"_  

Day 90... (The consultancy has been offboarded now)  
> Permie: _"I can't support this, I don't understand how it works..."_ 

And the rebuild commences!

Look, I don't have a problem with consultancies or service providers.  They have their place, they have useful knowledge and experience.  But they aren't doers in the context of your business.  It's the difference between theory and practice.  It is useful, nay necessary, to study and understand theory.  But practicing the theory in the context of your business tells you what works and what doesn't, this process takes time and effort - expensive commodities when you engage a third party.

What I do have a problem with is public sector companies refusing to give valued employees a £10k pay rise whilst writing writing cheques each year to _\<insert consultancy name here\>_ for £100k's (more on this topic in a later post I'm sure - it triggers me).

## Conclusion
There isn't one.  This post was a summary of some of my frustrations and experiences. If any of this resonated with you, I'd be more than happy to hear from you at helpfulghostwriter@proton.me.

## What's next?
The title of this post suggests it's incumbent on me to propose some solutions. But before I can do that I think I need to at least attempt to break down the problem statement a bit further...
