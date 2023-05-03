---
title: "Safety Culture and DevOps"
image: "https://cdn.mikeberry.dev/images/post/title-B-17-crash.jpg"
author: "Mike Berry"
date: 2023-05-02T00:00:00Z
description: "What is safety culture? How does it apply to DevOps and Software Engineering? What lessons can we learn from it?"
categories: ["DevOps"]
tags: ["Agile", "DevOps", "Safety Culture"]
featured: true
draft: false
---

## Introduction
One of the things I love about DevOps is the broad base of knowledge that the principles and practises come from. While much of the original thinking around Agile was tied to software development, DevOps has always taken the wider view of improving the overall system. It uses ideas taken from Lean manufacturing in Japan and Safety Culture in the airline industry. DevOps builds on the work of management thinking pioneers Peter Drucker and W. Edwards Deming and applies them in the context of modern software management.

If you work in technology, you are probably aware of the implementation side of DevOps such as continuous integration/continuous deployment (CI/CD) or infrastructure as code. You may even be familiar with some of the practises like microservices or monitoring and logging. Less well known are some of the high-level principles. For instance, do you know how safety culture has influenced DevOps?

These "higher level" principles are incredibly beneficial to learn and understand particularly if you work in a very dynamic or innovative space. While innovation requires you to discover the answers as you progress; having a good store of principle-based knowledge can greatly improve your success. These principles are typically centred in the **why**. They clarify the **why** behind the DevOps practises, rather than that the more detailed **what** of guides and instructions.

Therefore, I present to you my guide to Safety Culture. What is safety culture? How does it apply to software engineering? And what lessons can we learn from it?

## B-17 flying fortress
We begin our journey of understanding in 1943 over the English Channel inside a B-17 returning from a bombing mission. The B-17's long range, large bomb capacity and defensive armament made it a formidable weapon in the Allied arsenal. The B-17's typically flew in formations of 20 planes to increase protection for the bombers. Even so it was still a dangerous business - on average 1 in 20 B-17s would be lost on each mission.

At the end of a successful mission, you can imagine the relief of the crew of 10 (including 2 pilots) passing over the Cliffs of Dover ready to get some rest after more than 6 hours of stressful flying. As the plane approaches the runway it unexpectedly drops toward the ground and crash lands with the landing gear still up. As the bruised and broken crew emerge from the plane wreckage they wonder. How did a routine landing suddenly go so wrong?

![Crashed B-17](https://cdn.mikeberry.dev/images/post/B-17-crash.webp)

The answer to "what went wrong" for most of these similar accidents was recorded as 'pilot error'. Due to stress, trauma or just incompetence the pilot had made a mistake on the landing approach that put their life and the lives of their crew in jeopardy. In a 22-month period the Air Force had reports of over 400 similar incidents where pilot error led to damage, injury or in some cases death. It wasn't until after the War that further investigation was done into these incidents.

![B-17 cockpit controls](https://cdn.mikeberry.dev/images/post/B-17-controls.webp)

Alphonse Chapanis (an Airforce psychologist) recognized that the design of the cockpit controls contributed to confusion and mistakes<sup>[1](#references)</sup>. He noted that the flaps and landing gears had identical switches and were in the same area in the cockpit. During the high-workload period on the landing approach pilots would retract the landing gear leaving the flaps in place. Chapanis solution was to design new controls. The landing gear became a lever with a circle knob at the end, while the flaps a large lever with a square end. Once the new controls were successfully designed and installed no further similar incidents occurred. This "shape coding" of the cockpit controls is still in use today and was one of the first examples of applied ergonomics or human factors in design.

![Modern cockpit controls](https://cdn.mikeberry.dev/images/post/modern-controls.webp)

In 1947 Paul Fitts and Richard Jones built on Chapanis's work and looked deeper into this idea of 'pilot error'. Their study examined hundreds of incidents gathering extra information via recorded interviews and written reports. It had been assumed that these errors were due to poor pilot selection, training, or operations. The data Fitts and Jones collated did not match these assumptions. It appeared that pilots of all levels of experience and from a variety of cadres (training groups) sometimes made errors. Fitts and Jones refused to classify these events as 'failures' choosing to use the more neutral term 'experiences'.<sup>[2](#references)</sup>

They took the documented causes of 'pilot error' as the start of the investigation not the conclusion. What they found wasn't issues with 'bad' pilots but control, systems, and processes in need of re-design with "human factors" in mind. The pilot errors were the symptoms of the wider environment that person operated in. They occurred in the context of the tools, tasks, and operating environment at the time. Their findings centred on the design of the control system, the type of control used, the arrangement and labelling of controls, and the mental and physical demands of the tasks. These findings would greatly improve airplane safety and would become a landmark study in the world of safety culture.

We know that adding a poster to the wall that says "Don't crash planes" doesn't create safety. Only by investigating deeper into the environment are the real answers found. Yet somehow, it is still common to have 'human error' as the 'root cause' of an incident. Decades later organisations still struggle to understand and apply the lessons from safety culture.

## What is Safety Culture?

To understand safety culture, we must first learn about the two views of human error.<sup>[2](#references)</sup> The first view is the "Old View" also known as the 'Bad Apple' theory. The Old View sees safety problems as the result of a few bad apples in an otherwise safe system. These errors occur due to unreliable, unpredictable people who don't know or don't care to do the right thing. Safety rules, detailed procedures and inductions are supposed to help control this erratic behaviour. The Old View seeks to achieve safety through increased compliance to the processes and safety rules. Some inevitable human frailties can lead to issues that are solved by additional paperwork and reminders to be more safe!

Although this Old View has been prevalent in the last few decades of safety thinking, it is of limited usefulness and can even be counterproductive. In contrast the "New View" can help you build a safety culture that will make meaningful improvements to the safety of any organisation.

The basis of this New View is a psychological term called the "local rationality principle". A New View investigation always assumes people will make the logical decision that appears correct at the time given their circumstances. When following the New View, we don't rush to assign blame for the mistake made; we seek to understand why their actions made sense to the individual at the time.

| Old View | New View |
| --- | --- |
| Says what people failed to do | Tries to understand why people did what they did |
| Says what people should have done to avoid the outcome | Asks why it made sense for people to do what they did |

The B-17 story is an example of using the New View to provide insights that can greatly improve safety. This doesn't always come naturally and can take time and effort to learn. For example, what would you do in the following real-world scenario?

> Over a six-year period, 'hundreds of aircraft mechanics were cited for logbook violations. People working the aircraft on the gate were under pressure and they would screw up the paperwork.' Violations meant suspensions or a fine.<sup>[2](#references)</sup>

![Airplane Mechanics](https://cdn.mikeberry.dev/images/post/airplane-mechanics.webp)

How do you improve compliance in this important area? Do you increase fines? Add incentives? Or post a memo to remind mechanics logbooks are important?

The airline chose to visit the station that had most logbook problems. They asked the mechanics to create a new logbook page design. Another station made a few tweaks, and after the new logbooks were introduced, violations dropped to zero. The problem wasn't negligent mechanics, it was a poorly designed logbook.

A New View investigation doesn't rush to detail the chain of events and thereby declare the root cause.  Real insight is rarely found when investigations focus on went wrong in the past (the explanatory factors). Rather time is spent seeking to understand what changes are required for things to go right in the future (the change factors).

>In one mining operation, workers who maintained the big haul trucks were suffering from hand injuries. Each of these injuries was investigated and a report drawn up. It identified the typical explanatory factors: time pressure, people sticking their hands in places where they don't belong, lack of correct protective equipment, problems of light and visibility. These explanatory factors, however, did little to point the way to prevention or improvement. They suggested to people to stare harder, try more, follow the rules, be careful. None of that worked.<sup>[2](#references)</sup>

![Mining heavy Hauler](https://cdn.mikeberry.dev/images/post/heavyhauler.webp)

The change factor came when someone identified that more than 80 percent of the injuries occurred during unscheduled maintenance along the dusty roads of the mine not during scheduled maintenance in the shed. The company decided to invest aggressively in preventive maintenance (including a larger parts store), to ensure that as few trucks as possible would break down on the road. After it did this, hand injuries went down dramatically. The explanatory factors were not the same as the change factor.

## How does this apply to software engineering?

At this point you may be wondering what exactly airplane and mining safety has to do with DevOps? As you learn more about safety culture you will find many lessons that can easily be applied to the world of software development and operations. Perhaps the most obvious is the Post Incident Review (PIR). Some teams refer to these as a post-mortems, although I prefer to use the term PIR since dead bodies are generally not involved.

When the team at Google wrote the original [Site Reliability Engineering (SRE) book](https://sre.google/sre-book/introduction/) they dedicated a chapter to discussing their Blameless Culture. From Chapter 15 of the SRE Book we learn:

![Site Reliability Engineering Book](https://cdn.mikeberry.dev/images/post/SRE-book.webp)

> Blameless post-mortems are a tenet of SRE culture. For a post-mortem to be truly blameless, it must focus on identifying the contributing causes of the incident without indicting any individual or team for bad or inappropriate behaviour. A blamelessly written post-mortem assumes that everyone involved in an incident had good intentions and did the right thing with the information they had.

These SRE practitioners are clearly following the New View to better understand the incident and identify the change factors to create future safety. As the prevalence of software continues to grow across industries, the safe and secure operation of that software becomes even more important. Organisations from health care providers to financial organisations now rely on software to operate. Mistakes can be costly - like an [accidental transaction](https://www.cnbc.com/2022/09/08/citigroup-wins-appeal-over-mistaken-revlon-wire-transfer.html) that transferred $500 million causing Citibank 2 years of legal battles before it was returned. Outages can have an even bigger impact in our society. It's annoying if Twitter or Netflix is down, but if all payments at a bank fail thousands of families are unable to buy food or fill their cars up at the gas station.

These lessons from safety culture also apply to other areas beyond operations. Security teams working to keep your data safe can learn from safety culture, both in incident investigation and considering the "human factors" in secure system design. Professionals working in governance, risk, and compliance (GRC) can apply these lessons in designing and monitoring controls.

## Applying the lessons from Safety Culture
Having been introduced to the basic concepts of safety culture the next step is applying these concepts in your own team. We can draw on the years of experience gained by some of the world's leading safety organisations known as "High Reliability Organizations" or HROs. These organisations come from a variety of industries, yet they all work in environments with complex and hazardous systems which they operate error free. Research into these successful organisations shows that they share the same five characteristics. We will examine each of these characteristics along with discussing the fallacy of root cause and the importance of weak signals.

If that sounds of interest to you be sure to read part 2 of this deep dive into Safety Culture and DevOps. For now, I'll leave you with a table taken from [The Field Guide to Understanding 'Human Error'](https://www.amazon.com/Field-Guide-Understanding-Human-Error-dp-1472439058/dp/1472439058/)  by Sidney Dekker (Professor and Director of the Safety Science Innovation Lab at Griffith University in Brisbane, Australia). This article includes many quotes from his book, which I highly recommend purchasing if you are interested in delving deeper.

| Old View | New View |
| --- | --- |
| People seen as a problem to control | People seen as a resource to harness | 
| Focus on people's attitudes and behaviour | Focus on people's working conditions |
| Safety defined as absence of negative events (incident/injury free) | Safety defined as presence of positive capacities to make things go right |
| Whoever is boss or safety manager, gets to say | Whoever is expert and knows the work, gets to say |
| Dominated by staff | Driven by line |
| Guided by rules and compliance |  Guided by insight and context |
| Make it impossible for people to do the wrong thing | Give people space and possibility to do the right thing |
| Governed by process and bureaucracy | Adjusted by mutual coordination |
| Strives for predictability and standardization | Strives for diversity and innovation |
| Safety as accountability that is managed upward | Safety as a responsibility that is managed downward <sup>[2](#references)</sup> |

</br>

##### Recommended reading (and listening):

[Sidney Dekker, *The Field Guide to Understanding 'Human Error'* Third Edition](https://www.amazon.com/Field-Guide-Understanding-Human-Error-dp-1472439058/dp/1472439058/)

[Rethinking Safety - Podcast series by forensic engineer Sean Brady ](https://www.bradyheywood.com.au/podcasts/) 

</br>

##### References
1. [Alphonse Chapanis: Pioneer in the Application of Psychology to Engineering Design](https://www.psychologicalscience.org/observer/alphonse-chapanis-pioneer-in-the-application-of-psychology-to-engineering-design)
2.  Sidney Dekker, *The Field Guide to Understanding 'Human Error'* Third edition (London: CRC Press, 2014) pp. xix, 1, 19, 80, 163
