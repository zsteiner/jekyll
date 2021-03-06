---
title: UX Principles
author: Zach
layout: work-post
permalink: /2015/07/ux-principles-portfolio/
image: ux-principles.svg
description: I've maintained a living list of guiding principles for my UX work. The principles are a synthesis of established UX thought, applications of psychological research, and personal experience. Rather than keeping it in my head and on various white boards, I've formalized it as post on zachsteiner.com.
show-homepage: true
categories:
  - UX
---
Below is a living list of principles that guide my user experience work. I've maintained this list offline for sometime, but now seems a good time to share. These principles are not exhaustive by any means. Nor are they completely original. Some of the ideas are informed by my graudate coursework and research. Many are adapted from more experienced UX thinkers. I owe a lot of this list to Jakob Nielson's [10 Usability Heuristics][1], which motivated me to start the list. It's also surprising how little has changed in 20 years. Many of the other principles then coalesced through reading myriad articles/article, interactions with users, conversations with colleagues, and the odd memory from grad coursework. 

### Software is for humans...
*... and not the other way around*. Software is a tool created to help people solve some problem. A piece of software should be designed to solve said problem. A person should not have to redesign their behavior to suit the needs of software. This is manifest in small ways like requiring redundant data entry on a checkout form to major ways as when a convenient database design dictates an unnatural workflow. The line "What is easy for the developer, is rarely easy for the user" gets tossed around, but there is a lot of truth to it and speaks to the challenges of user-centered design. The hard work to discover user needs and build a solution to address their needs is well worth it. The even harder work of accepting feedback then iterating, refining, and never resting on our laurels is what truly helps us create person-centered software.
    
### Be "easy to learn", not "intuitive"
"Intuitive" is tossed around a lot in reference to software. [Lots of articles][2] will tell you how to add some intuitive pixie dust to your software and some even offer legitimately useful strategies for interface design. The problem is that software is not **inherently intuitive**. Many of us have built a rich experience (good and bad) with using software, however. Rather than assuming the user will know what to do intuitively, designers need to align with user expectations and help the user along in places where the software needs to be novel. Integrated, contextual [just-in-time learning][3] is a great alternative to manuals or training videos for those truly new or difficult interactions. It can be difficult to unlock the full power of complex software, but software need not be impenetrable. A properly designed experience can get a user doing the basics quickly while offering opportunities for discovery of more complex functionality. Well designed information architecture, clear UI copy, sensible defaults, and useful feedback can all contribute to this ease of learning. Logic Pro and Sketch both do this rather well considering the power/complexity of the software, especially compared to some statistics and design software that will go unnamed.
    
### Build trust
I previously researched trust in supervisor and organizations, but this concept seems underappreciated in UX. Building user trust should be a key a goal of UX design. User trust has big implications for user retention, purchasing behavior, and other metrics business care about. Thus, there is a great business case for building/maintaining trust in software. Though, trust is really easy to violate and notoriously difficult to rebuild. Violating user expectations or impairing user work can damage trust. Deleting a lot of work is a major violation, but small design choices can add up over time to violate trust (death by a thousand cuts). Interpersonal apology literature has applicable suggestions for strategies to rebuild trust ([Fehr & Gelfand, 2010][5]) when something goes wrong: 

1. Offer corrective action. That is, what will software do to make the situation right (this dovetails with offering forgiveness)
2. Demonstrating empathy. That is, show understanding of the situation and how the user may feel at the moment.

### Provide feedback
The core of building trust with any software is providing feedback. Software often completes tasks without letting the user know what just happened or provides confusing/vague/incomplete information. When a user saves her work, the software should provide that feedback. Beyond the basics, feedback is a great place to demonstrate empathy. Slack's [irreverent tone][4] is part of its success, but irreverence and emoji would likely come off as grating or tone deaf when used to report a system outage or deleting important files/records. A thorough understanding of the work to be done and the needs of users provides the basics what is appropriate in regard to tone of feedback. Some situations call for a sassy friend and some call for the friendly, but professional tone of a good doctor.
    
### Be transparent
This principle came from my observation of how many data systems operate. Often a user will enter some data and then it is sent into an apparent blackbox after hitting submit. Many systems forgo the basic reassurance that the data was actually saved. To further deepen the black box, finding previously entered data is often difficult to do. This makes it really hard for the user to trust her software. This is why many of the users I worked with could never conceive of going paperless; hard copies afforded them a sense of security and trust the software denied them. Beyond the frustration of iTunes changing user's carefully organized music libraries (and adding DRM), [much of the frustration toward Apple's iTunes Match][6] can be attributed to the lack of transparency. iTunes identifies music "automagically" (though often incorrectly) and then there is no transparency or offering of forgiveness (the next principle) once it is done. Whether we are dealing with a user's financial data or her carefully organized media collection, software should be upfront with what it is doing. If something goes wrong, we have the next principle.
    
### Offer forgiveness
Another principle borrowed from [Nielson][3]. So often software does a task and there is no going back. This impairs trust and fosters a culture of fear of software. Users become afraid to explore software because they don't want to "break something". People make mistakes and software should be sensitive to that. No button (or combination of buttons) should ever "break" a system. If a task truly offers no return, the software should adequately warn the user and allow an escape hatch before the critical moment. Don't be the software that allows a student to delete his term paper at 4am the day it is due. 

### Only be clever enough...
*... but not too clever*. Designers can become enamored with the novelty of new UI pattern or method of presenting information. At best, a user will likely not notice or care about the novelty of the UI. At worst, the task at hand may be obfuscated by the design choice (see any scrolling site that requires scroll down label or button). Early on, I often designed fussy UIs for the sake of trying something different. Through design iterations, many became drastically simpler and clearer to the user. This relates back to the first principle.

### Conserve precious cognitive resources
I took a grad seminar in training co-taught by a training expert and a cognitive psychologist that has stuck with me since. A major theme of the seminar was the notion of cognitive load. The human perceptual system and cognition are much more limited in bandwidth than we typically think. This is generally talked about at its most basic level in regard to working memory with the old chestnut: we can retain 7 items &plusmn; 2. This is not a hard and fast rule, let alone a law, and really only applies for arbitrary items (like 7 random digits or letters). The spirit of this chestnut, though, holds. Interfaces need to conserve the users limited resources of attention, memory, and cognitive processing. Anxiety and fear take up precious resources that can be used more productively. [Vague icons][7], byzantine navigation, unexpected/confusing interactions, lack of consistency, and many more interface blunders can increase the cognitive load of using software. Remember the user has a task she needs to accomplish.
       
### Don't induce nausea (or headaches)
This is a somewhat flippant phrasing for the important concept of accessibility. Some months ago I encountered an animated data visualization that literally made me dizzy and a bit queasy. I know a few people that feel dizzy viewing parallax animations. Apple ran into this issue for a subset of users with iOS 7 and had to compensate via user preferences. The goal is to help your users to feel comfortable while using software and being sensitive to not excluding a set of users. This covers everything from sensitivity to those with a tendency toward vertigo to designing for the visually impaired.


[1]: http://www.nngroup.com/articles/ten-usability-heuristics/
[2]: https://www.google.com/#q=intuitive+ux
[3]: http://www.nngroup.com/articles/stagnating-expertise/
[4]: https://medium.com/@awilkinson/slack-s-2-8-billion-dollar-secret-sauce-5c5ec7117908
[5]: http://dx.doi.org/10.1037/a0019993 
[6]: http://www.theverge.com/2015/7/1/8877129/apple-music-icloud-problems
[7]: http://thomasbyttebier.be/blog/the-best-icon-is-a-text-label