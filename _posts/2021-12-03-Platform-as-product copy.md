---
layout: fullpost
title: Platform as Product
summary: Notes from the Platform as Product training session.
series: notes
published: true
---

![image](https://user-images.githubusercontent.com/29025275/144725983-bec75ef4-92a1-456a-8266-1a84ca07318b.png)

- Traditional platform approach was to share services across teams, to reduce infra and tooling costs. A centralised approach. Cloud changed the paradigm.

- Standardisation was also a characterisitic of this traditional approach.

- Stream aligned teams increasingly being asked to take on more - increasing their cognitive load.

- Stream aligned teams need end to end ownership of their service and service lifecycle.

- So how can we balance giving full ownership without at the same time introducing a debilitating level of cognitive load --? PLATFORM AS A PRODUCT.

- Platform as a product MUST simplify tasks and workflows that teams need to build and run. It must reduce cognitive load. Reduce their need to understand underlying services.



### SECTION 1: Platform Value

- Any platform needs to add value to customers. What benefits are they getting? Look at value proposition canvas - https://www.youtube.com/watch?v=ReM1uqmVfP0

- Platform engineering requires long-term funding.

- Modern platform teams do not block, contrary to those that are request or ticket-based.

- Platform team provide internal services that abstract away low level concerns (infra provisioning, deployment pipelines, monitoring).

- Reduce the number of decisions an engineering team has to make - Spotify.

- Reduce team cognitive load.

- Provide useful abstractions for development teams.

- Takes complexity and simplifies it.

- Platform needs to be easy to understand, cover the relevant use cases and be available and scalable.

- Make the right thing the easy thing to do.

- Don't force teams to use the platform - provide optionality (where appropriate. In some cases, there aren't easy alternatives, such as IDM or Access Control).

- Teams are accountable for meeting governance targets. If they decide to go their own way, they need to take this responsibility.

- Standardizing for the sake of it can kill innovation.

- Provide multiple options. Teams can choose which options they want based on their own level of experiencel

- We need a way to measure the value we are providing.

- quarterly survey - agree or disagree to these statements (Twilio example). Or NPS.



### SECTION 2: Platform Customers

- Customers are teams using the platform services.

- Different teams have different needs. Maturity levels may be different.

- Develop personas to flesh out user needs.

- Build thinnest viable platform needed to deliver the value proposition. Smallest set of APIs, documentation, tools.

- Make time and room for discovery work


### SECTION 3: Platform Experience

- Internal users of your platform will have expectations based on their experience using common SaaS offering like Github etc.

- Once platform grows, we need to consider the consistency of the user experience provided. Separate teams within the same platform can lead to inconsistency. A shared set of principles and temmplates can help coherence. A UX enabling team could help here.

- Avoid a poor developer experience. 

- Jako Nielsen's ten usability heuristics.

- nordicapis.com Three principles of excellent API design.

- CLI guidelines (from ex Docker employees).


### SECTION 4: Platform Adoption Cycle

- Product adoption lifecycle.

- Crossing the chasm between early adopters and early majority requires work. Work closely with the early adopters to refine the solution so that is can cross the chasm.

- Measure platform adoption.

- Solve problems that drive adoption.

- Reduce friction for the early majority.

- Use semantic versioning to communicate changes.

- Don't worry too much about the laggards. Focus on optimising the 80% who use it.

- Selll the platform.


### SECTION 5: Summary

- Define platform value. Which team outcomes does the platform support? How does it simplify or accelerate the work of the engineering team? Better deployment frequency? Faster test execution? Simpler setup of new application environments? Easier access to data?

- Know your customers and define personas.

- Move from mandate to opt-in.

- Open the communication channels.

- Build a platform team with the product skills needed.




