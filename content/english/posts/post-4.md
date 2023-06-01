---
title: "Safety Culture and DevOps Part 2"
image: "https://cdn.mikeberry.dev/images/post/flight-operations.jpg"
author: "Mike Berry"
date: 2023-05-30T00:00:00Z
description: "What is safety culture? How does it apply to DevOps and Software Engineering? What makes High Reliability Organisations successful"
categories: ["DevOps"]
tags: ["Agile", "DevOps", "Safety Culture"]
featured: true
draft: false
---

## Introduction
Welcome to the second part of our two-part series on DevOps and Safety Culture. In case you missed it, we highly recommend going back and reading [Safety Culture and DevOps - Part 1](/posts/post-3/), where we explored some historical aspects of Safety Culture. In this article, we will review the research findings from successful organizations and apply it to software engineering.

## High Reliability Organisations
A sailor on an aircraft carrier, an air traffic controller, and a nuclear power operator. What do they all have in common? They all work in complex environments that are potentially hazardous, yet they continue to operate without major incidents. This is particularly impressive when considering the scale these groups operate at:

* ⭕ Each day the United States there are more than 45,000 flights and 2.9 million airline passengers who travel across 29 million square miles of airspace.<sup>[1](#references)</sup>
* ⭕ Across the United States there are currently 92 nuclear power reactors that account for ~20% of the electricity generated; second only to natural gas.<sup>[2](#references)</sup>
* ⭕ The US Navy operates 11 active service aircraft carriers, each one with a crew of roughly 4,000.<sup>[3](#references)</sup>

Aircraft carriers are particularly [demanding environments](https://www.youtube.com/watch?v=Ixwc-mFzhwU), flight operations occur 24 hours a day, seven days a week. This complex choreographed ballet of man and machine takes place on a flight deck many times smaller than a typical airport runway. Planes are launched off the deck at the same time as they are recovered. While waiting to launch planes refuel with engines running and live ordnance attached under their wings. The crew must carefully guide the planes to the launch catapult while avoiding the jet exhaust from planes and rotor downwash from helicopters. This all takes place on a flight deck that is constantly in motion on the open sea and covered in salt water.

Even with all the potential hazards mentioned above and others the US Navy has an excellent safety record. Likewise, both the US Nuclear Power industry and Air Traffic Control maintain high levels of safety and reliability. The question of how this is achieved led researchers from the University of Berkeley to study all three of these organisations to understand how they worked.

The researchers discovered that these organisations all shared the same five characteristics. It was these common characteristics that gave them the ability to operate in complex and high-risk environments, while still maintaining an excellent record of safety and reliability. This group of organisations are collectively known as **High Reliability Organisations** (HROs). Although the [initial research](https://journals.sagepub.com/doi/10.1177/108602668900300202) into HROs focused on these few high risk industries it has since expanded into other settings including health care and wildfire management.

Any organisation that operates in a complex environment can improve its reliability by understanding and applying the five HRO characteristics. For each of the characteristics below I've included both the definition and how it applies to software engineering. 

## 1. Sensitivity to operations
> HROs maintain a strong focus on their operations and are constantly monitoring and assessing the performance of their systems. They are quick to identify and respond to any deviations from expected standards.

**Performance**. What it is about a system that is most critical to monitor? We learn from Site Reliability Engineering (SRE) the concept of [Service Level Indicators (SLIs) and Service Level Objectives (SLOs)](https://sre.google/sre-book/service-level-objectives/). Used correctly the SLIs will help you understand the level of service you are providing to your users.

Monitoring what percentage of CPU a server is using does not help you understand performance. Similarly, only measuring if an API responds to requests is not useful if every response is a 500 error and your application is crashing. The metrics you monitor should align to the user experience as much as possible. For web/mobile applications this typically means tracking SLIs based on availability, latency, or throughput.

![Website Down](https://cdn.mikeberry.dev/images/post/techSupport.webp)

**Deviations**. You should be able to discover deviations in your system. What is a deviation? The answer is system dependant, but in a Kubernetes cluster it could be a list of containers that have very high restart counts. Sometimes a deviation is a lack of a metric. Low logins at 3am could be fine but a sudden 50% drop during peak period could point to login system issues.

## 2. Preoccupation with failure
> HROs are constantly aware of the possibility of failure and strive to identify potential problems before they occur. They emphasize proactive risk management and implement strategies to prevent or mitigate adverse events.

While the previous trait was about the current state of the system, a preoccupation with failure is about the future. Like an all-star team of Boy Scouts we need to ['Be Prepared'](https://en.wikipedia.org/wiki/Scout_Motto).

How do you prepare for failure? With the right design your system architecture can be both scalable and resilient. High performing teams go even further by following practises such as chaos engineering and running GameDays.

**Chaos Engineering** involves deliberately introducing disruptions and failures into your system such as shutting down services or increasing latency. This seemly paradoxical method works by controlling when and how the failure occurs. The [chaos experiments](https://netflix.github.io/chaosmonkey/) are carefully designed, tested, and then monitored as they are executed. This allows you to uncover and fix issues in a known environment before they become your next severity 1 outage.

**GameDays** are much like chaos engineering in that you are running a controlled experiment. The difference is that a GameDay is focused on people and teams. During the GameDay scenario teams respond to a simulated failure to see how they interact. GameDays are conducted as a collaborative effort involving multiple teams, including development, operations, and other relevant stakeholders. The evaluation includes how effective the incident response process was, clarity of communication between teams/stakeholders/users, and any other areas of improvement identified. Although the are called 'GameDays' most scenarios only take a few hours to run.

## 3. Reluctance to simplify
> HROs recognize the complexity of their environment and avoid oversimplifying problems. They invest time and resources in understanding the underlying causes of issues and developing nuanced solutions.

When incidents occur, we want to use that opportunity and extract the maximum amount of learning to improve future resilience. Having a **blameless culture** is key to capturing this learning. If we blame or penalise engineers who make mistakes, we both damage the workplace culture and decrease resilience. Blame and finger-pointing create a hostile and unproductive work environment where teams avoid being drawn into problems. Valuable information about issues is lost or remains hidden as even the smallest mistakes are concealed from others.

You may wonder, does this lack of blame reduce accountability? Not at all. By abandoning the need to blame we transform the accountability from backward facing to forward looking. By focusing on the future, we can better understand the detail surrounding the incident and can implement meaningful remediation actions.

Using a standard template is great way to improve your team's **Post Incident Reviews** (PIR). While many good templates exist, a popular template I recommend comes from the [SRE Handbook](https://sre.google/sre-book/example-postmortem/). It is well formatted and includes space for key information such as an incident timeline and lessons learned.

## 4. Deference to expertise
> HROs value the input and expertise of their employees and encourage a culture of open communication. They recognize that individuals closest to the work are often best positioned to identify and solve problems.

You may have heard of the HiPPO decision making process before. That is when decisions are made by following the Highest Paid Person’s Opinion (also known as the authority bias). HROs seek to involve many voices in decisions, taking care to get input from those with both expertise and experience in that area without regard to hierarchy.

Deference to expertise also relates to informal communication and learning. During the design of Apple Park (Apple's headquarters in Cupertino) Steve Jobs worked with architect Norman Foster to design many common spaces. The layout building and grounds purposefully encourages informal interaction and collaboration between different teams and departments.

![Website Down](https://cdn.mikeberry.dev/images/post/apple-park.webp)

While we may not have the luxury of designing a new office, we can still find ways to informally share expertise. Many organisations have success embedding resources in teams like an architect or platform engineer. While they still belong to a large group of architects they sit with and join in with their embedded team for their day-to-day work.

## 5. Commitment to resilience
> HROs prioritize building resilience into their systems to enable quick recovery from failures. They are prepared to adapt to changing circumstances and adjust their processes as necessary.

When building resilience into software there are many practises to consider:

- **Redundancy via Replication**: If one component fails, the system should continue operating without significant disruption.
  
- **Fail Fast and Failover**: Failures should be quickly detected, and traffic moved to alternate resources.

- **Fault Isolation and Containment**: Failures should be isolated to contain their impact. 

- **Graceful Degradation**: The system should gracefully degrade its functionality in the face of failures or high loads. 

- **Load Balancing and Scaling** Workloads should be distributed across multiple servers or instances to handle increased demand and prevent overloading individual components. 

Having a commitment to resilience isn't just about high availability architecture, you need to start with a solid foundation and adjust over time. Why would you build a globally load balanced and replicated system for an application that has 20 users in one location? When you build for change you can start small adding scale and redundancy as you grow.

So how can you create an application with the right attributes to change and evolve over time? The answer is in two very similar practises. The **The Twelve Factor App** and **Cloud Native Architecture**:

- ⭕ The original Twelve Factor App information was presented over 10 years ago, yet the list remains very relevant today. You can read about all twelve factors on the dedicated [Twelve Factor App website](https://12factor.net/)

- ⭕ Cloud native applications use many of the practises from the Twelve Factor list and adds some additional focus on making the most from the cloud. This article about [Cloud-Native Architecture](https://cloud.google.com/blog/products/application-development/5-principles-for-cloud-native-architecture-what-it-is-and-how-to-master-it) by Tom Grey (Google Cloud architecture expert) gives a great summary.

## Always learning
With time and commitment, any organisation has the potential to become a High Reliability Organisation (HRO) by embodying all five characteristics. Among these traits emerges a central theme - HROs are learning organisations. Never content with their current knowledge and skills, they constantly experiment, learn, and improve. While most technology organisations do not face life-or-death decisions daily, the lessons from HROs remain very relevant to any high performing technology team.

Having gained insight into Safety Culture and HROs, you are now ready to apply that knowledge in your own team. Start small. Achieving early, small victories generates the momentum necessary for significant changes in the future.

Consider the lessons above as a source of inspiration rather than a checklist. There is still much more to discover through your own learning and testing. Having a solid foundation of knowledge is an excellent starting point for embarking on your own journey of experimentation and acquiring invaluable firsthand experience.

For those who have made it all the way to the end and remain interested. I have some recommendations for further listening, reading, and watching.

### Bonus resources:
The [Rethinking Safety Podcast](https://www.bradyheywood.com.au/podcasts/) is a great resource for understanding more about HROs and each of the 5 characteristics. I particularly recommend episodes 5 and 6, if you want to skip the first few.

Also mentioned in part 1 of safety culture is [The Field Guide to Understanding 'Human Error'](https://www.amazon.com/Field-Guide-Understanding-Human-Error-dp-1472439058/dp/1472439058/) by Sidney Dekker. This is a great resource for anyone interested in delving deeper into Safety Culture.

Finally, for anyone who enjoys a good tech troubleshooting story, the following video comes from my former workplace the ANZx team. The video should give you some understanding of what it means to work in an organisation that demonstrates many of the five HRO characteristics. [More Questions than Answers. Dom Finn, Principle SRE, ANZx](https://youtu.be/UEgYdB3KPrc). 

##### References
1. [US Federal Aviation Administration - Air traffic by the numbers](https://www.faa.gov/air_traffic/by_the_numbers)
2. [Nuclear explained - U.S. nuclear industry](https://www.eia.gov/energyexplained/nuclear/us-nuclear-industry.php)
3. [How Many Active Aircraft Carriers In The Us Navy?](https://www.ussjpkennedyjr.org/how-many-active-aircraft-carriers-in-the-us-navy/)
