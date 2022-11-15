---
title: "Is DevOps Dead?"
image: "images/post/devops-conference.jpg"
author: "Mike Berry"
date: 2022-11-12T00:00:00Z
description: "Is DevOps Dead? What is Platform Engineering? Can it improve developer experience, and will it replace DevOps?"
categories: ["DevOps"]
tags: ["Agile", "DevOps", "Platform Engineering"]
featured: true
---

# Introduction
In 2015 the DevOps movement was gaining momentum. The DevOpsDays conferences were expanding around the world, from 22 events in 2015 to 42 the following year. The ["State of DevOps (2015)"](https://www.devops-research.com/research.html) report had companies of all sizes talking about how to “deploying 30x more frequently with 200x shorter lead times”.

Amid this DevOps excitement, I decided to start a DevOps Guild. A companywide internal community to share DevOps leading practises. Organising a meeting was the easy part; the hard part was finding the right people to join me. I needed to find people who would contribute and help build the community.

I decided on an experiment. I booked a meeting space for 200 people and invited 11 people to attend. No, this was not ahead of its time social distancing. I had a plan. Each person I invited came from various parts of the company and all were doing excellent DevOps work in their own areas. The invite came with a request to please suggest others to join us. The first group of 11 invited 32 more who then invited another 59. At this point the word was out and 25 additional people asked to join in. From that group of 11 we ended up with a total of 127 committed attendees who were interested in joining what became the first of many DevOps guild meetings.

![The DevOps Guild](/images/post/DevOpsMeeting.svg)


That first meeting was over 7 years ago now. In 2022 the DevOps movement is bigger than ever. What began with a [single DevOpsDays conference](https://www.youtube.com/watch?v=o7-IuYS0iSE) in Ghent in 2009 expanded to include 80 conferences around the world in 2019. As you can see from the Google Trends data below, there has never been more interest in DevOps.

![DevOps - Google Trend data](/images/post/devops-google-trend.webp)

So, if DevOps has become so popular, why all the recent talk that **“DevOps is Dead”**?

- [The New Stack - DevOps Is Dead. Embrace Platform Engineering](https://thenewstack.io/devops-is-dead-embrace-platform-engineering/)
- [TechBeacon - Has DevOps turned development into a juggling act?](https://techbeacon.com/app-dev-testing/has-devops-turned-development-juggling-act)
- [InfoWorld - Devs don’t want to do ops](https://www.infoworld.com/article/3669477/devs-don-t-want-to-do-ops.html)
- [Honeycomb.io - The Future of Ops Is Platform Engineering](https://www.honeycomb.io/blog/future-ops-platform-engineering)

## DevOps Disillusionment

### DevOps Theatre
One of the inevitable issues with increased popularity is the likelihood of leaders becoming excited about the DevOps hype and missing the substance of the movement. Applying DevOps practises will make significant [ongoing improvements](https://www.atlassian.com/devops/what-is-devops/benefits-of-devops), but they often need a substantial period of cultural change. And as it turns out, cultural change is extremely hard. It takes time, strong leadership and engaged teams.

What happens when your company decides to jump into DevOps without first understanding what DevOps is? You get - DevOps Theatre.

DevOps theatre is much like its cousin - Agile Theatre. That is when your “agile transformation” only involves the most visible parts of Agile. You have a daily stand-up, you plan 2-week sprints, your office walls are overloaded with sticky notes and planning includes creating points which you burn later in the week. Sadly, behind all that agile effort, Agile Theatre misses the substance. The daily feedback does not alter decisions, tasks rarely complete when estimated and the only impact to your daily work is the added overhead of admin in Jira.

[![Daily Stand-up](/images/post/dailystandup.webp)](https://medium.com/hackernoon/scrum-gone-wild-in-15-cartoons-cca23937a183)

Likewise, DevOps theatre can be recognised by the prevalence of the appearance of change without the substance. Typically, it involves purchasing many, many DevOps tools that create as many problems as they solve. You create separate DevOps team full of DevOps engineers to manage the new tools sprawl and build complex deployment pipelines. Your CI/CD process becomes like a “choose your own adventure” story with diverging paths of bash scripts, where occasionally a bear devours your code. DevOps theatre runs on Kubernetes (which you always call k8s “Kates”), it has a dashboard and an impressively large AWS bill.

For all those poor teams stuck in DevOps theatre, you can understand why they do not love DevOps.

### Do it all Developers
Developers are tiring of the idea that they should be doing both the development and operational work because (in the words of Werner Vogels Amazon CTO) “If you build it, you run it.” This sentiment came from the early days of DevOps when team worried about “the wall” between development and operations. The intent was to bring the two teams closer together in terms of skillsets and communication. The ops team use more 'dev' skills like configuration as code to do their work. Similarly, the dev team give more consideration to 'ops' concerns like instrumenting code to work with Open Telemetry.

![Developers and Operations personalities](/images/post/devandops.webp)

Closer communication and swapping skills make sense, but does DevOps mean developers support production? Do you need to have your development team ready to be paged? Does DevOps demand developer devotion to daily (ops) duties? Maybe.

There is significant value in the development team helping to “run” the software they are building. The developers move closer to the customer; they can better understand feedback and see the impact their choices have on production systems. Even so there is a balance to strike between giving every task to the development team and having developers do nothing but code new features. This balancing of responsibilities can be tricky, which is why there is growing interest in a solution often referred to as - Platform Engineering.

## Platform Engineering
Platform Engineering takes the lessons learnt from DevOps and creates a new operating model. A way of working that is optimised for teams creating cloud native software.

![Gartner Hype Cycle 2022](/images/post/HypeCycle.webp)

I first [started discussing](https://www.meetup.com/devops-melbourne/events/237351113/) the need for a Platform Engineering team in 2017. After some organisational wrangling, we had the first team up and running the following year. Since then, the team has continued to expand in both in size and responsibility. This operating model started even earlier in Silicon Valley. In 2015 Google worked with the Cloud Native Computing Foundation (CNCF) to release Kubernetes 1.0. Kubernetes was heavily influenced by the Google’s [cluster management platform](https://www.youtube.com/watch?v=0W49z8hVn0k) - “Borg.” That same year Netflix released their own open-source project - ([Spinnaker](https://spinnaker.io/)) a continuous software delivery platform. Both open-source projects the result of years of effort by their respective Platform Engineering teams.

*What exactly is a Platform Engineering team and what problems do they solve?*

### Everything is code
There is nothing I love more than a beautiful and functional user interface (UI). Even so, when I configure any kind of software, infrastructure, or network I want to use code not the UI. From interacting with SaaS via APIs to configuring cloud environments with Terraform, everything is moving away from [ClickOps](https://www.august.com.au/blog/killing-click-ops-what-it-is-why-its-problematic-and-how-to-avoid-it/) (user interface driven) towards configuration via code (sometimes called [GitOps](https://www.gitops.tech/)). No more waiting for the right person with admin access to click around inside a UI to make changes for you. The configuration has moved into the repository, where it can be tracked and automated.

The Platform Engineering team are typically the experts at configuring both Terraform and Kubernetes. They may even write their own CLIs (command-line interfaces) or other software to help automate repetitive tasks.

### Reducing friction
The Platform Engineering team should not be treated as another team that stand in the way of getting code into Production. They should be the team that create the “paved road” for developers to deploy their own code. The team improve the CI/CD (continuous integration/continuous delivery) process. The tools they build are self-service and include automated checking, no longer requiring manual reviews as policies are automatically validated.

Careful ongoing product management of the platform is required as the team cannot build everything at one. Only the most valuable DevOps “jobs to be done” can be prioritised. For example, the team should not invest time making it easy build and deploy Rust apps if most of the engineers are building services in Go.


### Developer Experience
The third area of consideration is Developer Experience (DevEx). This can be a broad area that includes everything from the onboarding experience and laptop setup thorough to the ease of code deployment and troubleshooting.

A Platform Engineering team can help optimise and fix issues that can improve the development experience across teams. Spotify have invested in this area and created a developer portal called [Backstage](https://backstage.io/). Backstage is particularly useful if you work in a large company with many teams of engineers working and build software together. A clear example of the benefits a Platform Engineering team can bring.

![Spotify - Backstage](/images/post/backstage.webp)

## The final verdict - Peak DevOps?
Is DevOps dead - no. DevOps is still popular and will continue to be discussed for years to come. Platform Engineering is not going to replace DevOps. Platform Engineering will continue to be an opinionated subset of DevOps practises slowly increasing in popularity as more companies come to see the benefits of these platform teams.

I do wonder though if we are experiencing peak DevOps? Now that the DevOps ideas and practises have become so ubiquitous *DevOps* has become less and less of a useful term. Is there a better way to group together the principles and practises that high performing teams use to build software? A way to include a broader set of practises like Lean, Agile, Site Reliability Engineering (SRE), Security, Safety Culture, Platform Engineering and of course DevOps?

### Velocity Engineering?
When I first started talking about platform engineering teams, I referred to the idea as Velocity Engineering. Maybe Velocity Engineering’s time has come as the new DevOps with less buzzword baggage attached? What do you think? Have we reach peak DevOps? Should we start talking about Velocity Engineering practises? Or is DevOps here to stay?

While you are pondering that, be sure to watch this great song by **Forrest Brazeal**:

{{< youtube yDcaRklX7q4 >}} <br>

If you are interested in learning more about Platform Engineering and DevOps check out:  
[How Internal Developer Platforms improve the Developer Experience](https://humanitec.com/blog/gartner-internal-developer-platforms-platform-engineering)  
*Further information about Platform Engineering*

[How Netflix Thinks of DevOps(2016)](https://www.youtube.com/watch?v=UTKIT6STSVM)  
*An old, but fun conference talk by Dave Hahn.*

[DevOpsDays Events](https://devopsdays.org/events)  
*Conferences are slowly coming back post-pandemic.*