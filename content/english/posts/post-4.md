---
title: "Saftey Culture Part 2"
image: "images/post/.jpg"
author: "Mike Berry"
date: 2023-04-24T00:00:00Z
description: "What is safety culture?"
categories: ["DevOps"]
tags: ["Agile", "DevOps", "Safety Culture"]
featured: false
draft: true
---
### Notes

Cultural Damage - The importance of safety culture

ChatGPT
Safety culture in DevOps is crucial as it helps to ensure that systems and processes are designed and implemented in a manner that prioritizes the well-being and protection of people, organizations, and the environment. This includes promoting a proactive approach to identifying and mitigating potential risks, promoting collaboration and communication among team members, and continuously monitoring and improving processes. By prioritizing safety culture, organizations can prevent incidents, ensure compliance with regulations, and ultimately, protect the reputation and success of their operations.

High Reliability Organizations (HROs) are organizations that operate in complex and high-risk environments, yet manage to maintain an excellent record of safety and reliability. They share five key characteristics, which are:


References

p125 Deepwater Horizion 0 accidents
https://www.faa.gov/air_traffic/by_the_numbers
https://www.eia.gov/energyexplained/nuclear/us-nuclear-industry.php
https://www.youtube.com/watch?v=Ixwc-mFzhwU - Inside World's Most Dangerous Workplace: US Aircraft Carrier Flight Deck
https://sre.google/sre-book/service-level-objectives/
https://en.wikipedia.org/wiki/Scout_Motto
https://netflix.github.io/chaosmonkey/
https://sre.google/sre-book/example-postmortem/

Ideas

The new way of thinking (no bad apples)
High reliability organisations


The falicy of root cause - Causal diagrams
importance of Weak signals



## Introduction


## ??history
A sailor on an aircraft carrier, an air traffic controller and a nuclear power operator. What do they all have in common? They all work in environments that are complex and potentially hazardous yet they continue to operate error free. The scale these groups operate at is easily overlooked:

- Every day in the United States more than 45,000 flights and 2.9 million airline passengers move across more than 29 million square miles of airspace.

- The United States currently has 92 nuclear power reactors that account for ~20% of the electricity generated; second only to natural gas.

- The US Navy currently has around 11 active service aircraft carriers, each one with a crew of 4,000+.

Aircraft carriers are particularly demanding environments as flight operations occur 24 hours a day, seven days a week. This complex choreographed ballet of man and machine takes place on a flight deck many times smaller than a typical airport runway. Planes launched off the deck at the same time as they are recovered. While waiting to launch planes refuel with engines running and live ordanance attached under wing. The crew must carefully guide the planes to the launch catalput while avoiding the jet exhaust from planes and rotor downwash from helicopters. This all takes place on a flight deck that is constantly in motion on the seas and covered in salt water.

Even with all the potential hazards mentioned above and others the US Navy has an excellent safety record. Likewise both the US Nuclear Power industry and the US Air Traffic Control maintain a high levels of safety and reliability. The question of how this was possible led researchers from the University of Berkeley to study all three of these orgnisations to find out more about how they worked.

The researchers discovered that these organisations all shared the same five characteristics. It was these common characteristics that gave them the ability to opeat rate in complex and high-risk environments, while still maintaining an excellent record of safety and reliability. These organisations are collectively know as **High Reliability Organisations** (HROs). Although the [inital research](https://journals.sagepub.com/doi/10.1177/108602668900300202) into HROs focused on high risk industries it has since expanded into other settings including health care and wildfire management.

So what are these 5 characteristics and how do they create a highly reliable organisation? Along with each characteristic I will also share some ways this can be applied in teams building and running software.

## Sensitivity to operations
> HROs maintain a strong focus on their operations and are constantly monitoring and assessing the performance of their systems. They are quick to identify and respond to any deviations from expected standards.

Logging and Monitoring is a standard practise in most technology teams and there are a myriad of modern tools avaiable to help you with this task. To really live ideal of 'sensitivity to operations' I want to focus on two words from the desription.

**Performance**. What it is about a system that is most critical to monitor? We learn from Site Reliability Engineering (SRE) the concept of **service level indicators** (SLIs) **Service Level Objectives** (SLOs). Used correctly the SLIs should help you understand the level of service you are providing your users.

Monitoring if a server is running, or if is using more then 90% of avalible CPU doesn't help you understand performance. Likewise only measuring if an API is runnning and responding to requests isn't useful if every respose is a 500 error and your application is crashing. What you monitor should align to the user experience as much as possible. For web/mobile applciations this typically means tracking SLIs based on availability, latency, or throughput.

**Deviations**. This is the other interesting area in regards to monitoring. You should have the ability to discover deviations in your system. What is a deviation? Obviously it depends on the system, but in a Kubernetes cluster it could be a list of containers that have very high restart counts. Sometimes a deviation is a lack of a metric. Low logins at 3am could be fine but a sudden 25% drop during peak period could point to login system issues.

## Preoccupation with failure
> HROs are constantly aware of the possibility of failure and strive to identify potential problems before they occur. They emphasize proactive risk management and implement strategies to prevent or mitigate adverse events.

While the previous trait was about the current status of the system, a preoccupation with failure is about the future. Like an all-star team of Boy Scouts we need to 'Be Prepared'.

How do you prepare for failure? There are many patterns to follow to make sure your architecture is both scalable and resilient. You can go even further by following practises such as chaos engineering and running GameDays.

**Chaos Engineering** involves deliberately causing disruptions and failures into your system such as shutting down services or increasing latency. **This may sound like a bad idea, but this is performed in a very controlled way.** The chaos experiments are carefully designed, tested and then monitored as they are executed. This allows you to uncover and fix issues in a controlled enviornment before they become your next severity 1 outage.

**GameDays** are similar to chaos enginerring in that you are running a controlled experiment. The difference is that a GameDay is  focused on the people and teams working in the system. On the GameDay teams will need to repond to a simulated failure scenario to see how they respond. Luckily the GameDay is not typically a full day; it only takes a few hours to run.

GameDays are conducted as a collaborative effort involving multiple teams, including development, operations, and other relevant stakeholders. The evaluation includes how effective the incident response process was, clarity of communication between teams/stakeholders/users, and any othere areas of improvment identified.

## Reluctance to simplify
> HROs recognize the complexity of their environment and avoid oversimplifying problems. They invest time and resources in understanding the underlying causes of issues and developing nuanced solutions.

We covered seome elements of this in the previous safety culture article regarding how to run post incident investigations. When issues do occur we want to use that opportunity and extract the maximum amount of learning to improve future resiliance.

This is one reason why a **blameless culuture** is important. If we blame or penalise engineers who make mistakes we both damage the workplace culture and decrease resiliance. As we have seen, safety is not increased by telling practitioners to "be more safe". Blame and finger-pointing create a hostile and unproductive work environment in which teams avoid problems. Valuable infomation about issues is lost or remains hidden as even the smallest mistakes are covered over and hidden from view.

DEEPWATER

You may wonder if this culture reduces accountability? The goal is not to reduce accountability, but to transform it from backward to forward looking accountability. By putting aside blame we can focus on understanding the incident and planning meaningful remediation.

There are many tools and templates avaible to assist in how to best run a Post Incident Review (PIR). A popular template I recommend comes from the SRE Handbook. It has a number of good features of which I think the "Lessons Learned" and "Timeline" are both must have sections in any PIR process.

## Deference to expertise
> HROs value the input and expertise of their employees and encourage a culture of open communication. They recognize that individuals closest to the work are often best positioned to identify and solve problems.

You may have hear of the HiPPO descison making process before. That is when decisions are made by following the Highest Paid Person’s Opinion (also know as authority bias). HROs seek to involve many voices in decisions, taking care to get input from those with expertise or recent experience in that area.

Deference to expertise also relates to informal communication and learning. During the design of Apple Park (Apple's headquerters in Cupertino) Steve Jobs work with architect Norman Foster to design many common spaces. The layout building and grounds purposfully encourages interaction and collaboration between different teams and departments.

While we may not have the luxury of designing a new office we can still find ways to informally share expertise. Many organisation have success embeding resources in teams like an architect or platform engineer. While they still belong to a large group of architects they sit with and join in with their embeded team for all of their day-to-day work.

## Commitment to resilience
> HROs prioritize building resilience into their systems to enable quick recovery from failures. They are prepared to adapt to changing circumstances and adjust their processes as necessary.

Resilience is software if often considered in terms of ability to scale to meet demand and ability withstand failure events. This is high avaiability architecture is enabled by many patterns such as Load Balancing, Caching, Throttling, Circuit Breaker and Leader Election. All of these patterns and more are important to conside as your application scales up.












If you are interested in learning more about Platform Engineering and DevOps check out:  
[How Internal Developer Platforms improve the Developer Experience](https://humanitec.com/blog/gartner-internal-developer-platforms-platform-engineering)  
*Further information about Platform Engineering*
