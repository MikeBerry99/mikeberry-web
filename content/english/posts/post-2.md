---
title: "Is DevOps Dead?"
image: "images/post/devops-conference.jpg"
author: "Mike Berry"
date: 2022-11-09T00:00:00Z
description: "DevOps isn't dead. Platform engineering is "
categories: ["DevOps"]
tags: ["Agile", "DevOps"]
featured: true
---

# Introduction
Back in 2015 and I had a problem. I wanted to kick-start a companywide DevOps community/guild. It was a great time for it. Our city's ["DevOpsDays Melbourne"](https://legacy.devopsdays.org/events/2015-melbourne/) conference would be held in a few months. One of 22 DevOpsDays conferences that would be hosted around the world in 2015. Even outside the tech start-up scene DevOps was gaining momentum. The ["State of DevOps"](https://www.devops-research.com/research.html) report had companies of all sizes where talking about how to "deploying 30x more frequently with 200x shorter lead times".

I was working inside a large company with several thousand people working in technology. Large companies have the benefits of lots of resources, but that often comes at the cost of lots of bureaucracy. So how do I find a group of committed people who will be willing to join in, share ideas and work to create a DevOps community? I decided to try an experiment. I booked a meeting space with room for 200 people and then I invited 11 people to attend. No, this wasn't some kind of next level social distancing; it was all part of the experiment. You see I selected the 11 invitees very carefully. Each one I knew came from different parts of the company and all were doing great DevOps work in their own areas. Each invite came with a request to please suggest others to join us. The initial 11 people invited a further 32 and that group invited a further 59. At this point the word was out and 25 more people asked to join in. From that group of 11 we ended up with a total of 127 committed attendees who were interested in joining what became the first of many DevOps guild meetings.

![The DevOps Guild](/images/post/DevOpsMeeting.svg)


That first meeting was over 7 years ago now. In 2022 DevOps is bigger than ever. What began with a [single DevOpsDays conference](https://www.youtube.com/watch?v=o7-IuYS0iSE) in Ghent in 2009 expanded to include 80 conferences around the world in 2019. As you can see from the Google Trends data below, there has never been more interest in DevOps.

![DevOps - Google Trend data](/images/post/devops-google-trend.jpg)

So, if DevOps has become so popular, why all the recent talk that "DevOps is Dead"?

- [The New Stack - DevOps Is Dead. Embrace Platform Engineering](https://thenewstack.io/devops-is-dead-embrace-platform-engineering/)
- [TechBeacon - Has DevOps turned development into a juggling act?](https://techbeacon.com/app-dev-testing/has-devops-turned-development-juggling-act)
- [InfoWorld - Devs don’t want to do ops](https://www.infoworld.com/article/3669477/devs-don-t-want-to-do-ops.html)
- [Honeycomb.io - The Future of Ops Is Platform Engineering](https://www.honeycomb.io/blog/future-ops-platform-engineering)

## DevOps Disillusionment

### DevOps Theatre
One of the inevitable issues with greatly increased popularity is the likelihood of leaders getting caught up in the DevOps hype and missing the substance of the movement. Applying DevOps practises will make significant [ongoing improvements](https://www.atlassian.com/devops/what-is-devops/benefits-of-devops), but they often require a substantial period of cultural change. And as it turns out, cultural change is hard, very hard. It takes time, strong leadership and engaged teams.

What happens when your company decides to jump into DevOps without first understanding what DevOps is? You get - DevOps Theatre.

DevOps theatre is much like its cousin - Agile Theatre. That's where your "agile transformation" mostly involves doing all the most visible parts of Agile. You have a daily stand-up (that often takes 30min), you have 2-week sprints, all your office walls are overloaded with sticky notes, and you have weekly meetings with your team's agile coach about assigning points so they can be burnt down. Sadly, behind all that agile effort Agile Theatre misses the substance. The daily status doesn't change decision making, work rarely completes in sprint and your work is much the same as ever but with the additional overhead of daily task admin in Jira.

[![Daily Standup](/images/post/dailystandup.jpg)](https://medium.com/hackernoon/scrum-gone-wild-in-15-cartoons-cca23937a183)

Likewise, DevOps theatre can be recognised by the prevalence of the appearance of change without the substance. It typically involves purchasing many, many DevOps tools to proactively solve problems before you even have them. Then you need to hire a separate DevOps team full of DevOps engineers to manage the tools and build complex pipelines. Your CI/CD process is not so much basic workflows as it is more of a choose your own adventure story with diverging paths of bash scripts, where occasionally your code gets eaten by a bear. DevOps theatre runs on Kubernetes (which you always call k8s "kates"), it has a dashboard and an impressively large AWS bill.

For all those poor teams stuck in DevOps theatre, you can understand why they don't love DevOps. 

### Do it all Developers
Developers are tiring of the idea that they should be doing both the development and operational work because (in the words of Werner Vogels Amazon CTO) "If you build it, you run it". This sentiment came from the very early days when there were valid concerns about "the wall" between development and operations. The intent was to bring the two teams closer together in terms of skillsets and communication. The Ops team use more "dev" skills like configuration as code to do their work. Similarly the dev team give more consideration to ops concerns like instrumenting code to work with Open Telemetry.

![Developers and Operations personalities](/images/post/devandops.jpg)

Closer communication and swapping skills make sense, but does DevOps mean developers support production? Do you need to have your development team ready to be paged? Does DevOps demand developer devotion to daily (ops) duties? Maybe.

There is a lot of value in having the development team helping to "run" the software they are building. They move closer to the customer; they can better understand feedback and see the impact their choices have on production systems. Even so there is a balance to strike between giving every task to the development team and having developers do nothing but code new features. This balancing of responsibilities can be tricky, which is why there is growing interest in a solution often referred to as - Platform Engineering.

## Platform Engineering
Platform Engineering takes the lessons learnt from DevOps and creates a new operating model. A way of working that's optimised for teams creating cloud native software.

![Gartner Hype Cycle 2022](/images/post/HypeCycle.jpg)

I first [started talking](https://www.meetup.com/devops-melbourne/events/237351113/) about the need for a Platform Engineering team in 2017. I was working in a large enterprise at the time, so this was a new idea that took time to bring to life. Fortunately, we had the first team up and running the following year, which continued to expand in the years since. This method of working started even earlier in the Silicon Valley tech companies. In 2015 Google worked with the Cloud Native Computing Foundation (CNCF) to release Kubernetes 1.0. Kubernetes was heavily influenced by the Google's [cluster management platform](https://www.youtube.com/watch?v=0W49z8hVn0k) - "Borg". That same year Netflix released their internal continuous delivery software platform ([Spinnaker](https://spinnaker.io/)) as open-source software too.

*What exactly is a Platform Engineering team and what problems do they solve?*

### Everything is code
There's nothing I love more than a beautiful and functional user interface, but when I'm configuring any kind of software, infrastructure, or network I just want to use code of some kind. From interacting with SaaS via APIs to configuring cloud environments with Terraform, everything is moving away from [ClickOps](https://www.august.com.au/blog/killing-click-ops-what-it-is-why-its-problematic-and-how-to-avoid-it/) (user interface driven) towards configuration via code (sometimes called [GitOps](https://www.gitops.tech/)). No more waiting for the right person with admin access to click around inside a UI to make changes for you. The configuration is now inside the repository and now easily tracked and automated.

The Platform Engineering team are typically the experts at using Terraform and configuring Kubernetes clusters/deployments. They may even write their own CLIs (command-line interfaces) or other software to help automate repetitive tasks.

### Reducing friction
The Platform Engineering team shouldn't be treated as another team that stand in the way of getting code into Production. They should be the team that create the "paved road" for developers deploy code to production. While they do work on improving the CI/CD (continuous integration/continuous delivery) process, you shouldn't need to talk to them about your deployments. The tools they build are self-service and include lots of automated checking, so there's no need for the manual reviews every time and most policies are automatically validated.

Careful ongoing product management of the platform is required as the team can't build everything at one. Only the most valuable DevOps "jobs to be done" can be built. For example, the team can't invest time making it easy build and deploy apps built in Rust if the vast majority of the engineers are building services in Go.

### Developer Experience
The final area of consideration is Developer Experience. This can be a broad area that includes everything from the onboarding experience and laptop setup thorough to the ease of code deployment and troubleshooting.

A Platform Engineering team can help optimise and fix issues that can improve the development experience across teams. Spotify have invested in this area and created a developer portal called [Backstage](https://backstage.io/). Backstage is particularly useful if you are a large company with many teams of engineers working and build software together. It's a great example of the benefits a Platform Engineering team can bring.

![Spotify - Backstage](/images/post/backstage.jpg)

## The final verdict - Peak DevOps?
Is DevOps dead - no. DevOps remains popular and will be discussed for many years to come. Platform Engineering isn't going to replace DevOps. Platform Engineering will continue to be an opinionated subset of DevOps practises slowly increasing in popularity as more companies come to see the benefits of platform teams.

I do wonder if we are experiencing peak DevOps? Now that the DevOps ideas and practises have become so ubiquitous it has become less and less of a useful term. Is there a better way to group together the principles and practises that high performing teams use to build software? A way to include a broader set of practises like Lean, Agile, Site Reliability Engineering (SRE), Security, Safety Culture, Platform Engineering and of course DevOps?

### Velocity Engineering?
When I first started talking about platform engineering teams, I referred to the idea as Velocity Engineering. Maybe Velocity Engineering's time has come as the new DevOps with less buzzword baggage attached? What do you think? Have we reach peak DevOps? Should we start talking about Velocity Engineering practises? Or is DevOps here to stay?

While you are pondering that, be sure to watch this great song by **Forrest Brazeal**:

{{< youtube yDcaRklX7q4 >}} <br>

If you are interested in learning more about Platform Enginering and DevOps check out:

[How Internal Developer Platforms improve the Developer Experience](https://humanitec.com/blog/gartner-internal-developer-platforms-platform-engineering)  
Some further information about Platform Engineering

[How Netflix Thinks of DevOps(2016)](https://www.youtube.com/watch?v=UTKIT6STSVM)  
An old, but fun conference talk by Dave Hahn.

[DevOpsDays Events](https://devopsdays.org/events)  
Conferences are slowly coming back post-pandemic.