---
layout: fullpost
title: Team Topologies
summary: My highlights from the Team Topologies book.
series: notes
published: true
---

- Much has been written about the design of software, but little has been written about the design of the software organisation.

- This book is all about team structure and modes of interaction

- As a system gets more complex, so does the cognitive load of the teams working to support and evolve it.

- System design should cater for loose coupling and optimal flow.

##### Chapter 1

- Building systems is a team activity.

- Treat people and technology as a 'single human/computer carbon/silicon sociotechnical system'.

- Don't rely on the org chart to help understand how to split the work. Instead put in place long-lived, decoupled teams. Org charts and the strict communication channels they imply, don't represent reality. 

- In order to get work done, lateral (or horizontal) communication is necessary.

- We need to map out the actual communication patterns between teams and individuals, within our organisations.

- We should optimise team design for delivery of value to customers.

- Systems thinking - look at the whole ---> Find the biggest bottleneck --> Eliminate it.

- Three types of team structure - Formal, Informal, Value Creation. This book focuses on last two.

- Conway's law - Organisations are constrained to produce system designs that are copies of the communication structure of the organisation. Because this is what the communication channels allow.

- High cognitive load on teams prevents mastery attainment and increases context switching costs, introduces delays and quality issues. A team becomes the bottleneck.

- Put the team first! Restrict cognitive load and design the inter-communications patterns between them.

- An organisation organised into functional silos is unlikely to produce systems architected for fast flow. 

- By shaping the communication paths, we can avoid Conway's law. 

- "If we do not want a single shared database, or separate front end and back end tiers, 
we need to think again about our organisation design".

- Consider what software architecture we desire before designing our teams.

- We need a team-first architecture designed for people to work with it.

- Technical people need to be involved in organisation design.

- Identify where communication is happening when it shouldn't be - what is driving that? What gap is there?

- Speed of software delivery affected by the number of team dependencies the organisation design dictates.

- Fast flow means restricting communication.

- Fracture plan patterns split code up into separate parts that can live in separate repos and can be worked on by different teams.

- Reverse Conway - design teams to match the intended architecture. DBA example.

##### Chapter 3 - Team first thinking

- Google research - who is on the team matters less than the team dynamics.

- Team - 'Stable grouping of five to nine people who work toward a shared goal as a unit.'

- Work should be assigned to teams, not individuals.

- Maximise trust by limiting team numbers. Trust allows us to innovate and experiment.

- Dunbar's number.

- Brook's law.

- Teams then own software and should think in multiple horizons. Ownership is key. Every part of the system should be owned by one team.

- Every part of the software should be owned by one team only.

- We need to manage the cognitive load of each team carefully.

- Cognitive load - the total amount of mental effort being used in the working memory - Sweller, 1998.

- Intrinsic cognitive load can be minimised through training, good choice of technology, hiring etc., extraneous cognitive load should be eliminated or automated, leaving us room for germane cognitive load.

- Consider number and complexity of domains as a means of assessing your team's cognitive load. Amount of context-switching is an important factor.

- If a domain is too big for a single team, break the domain down. 

- Communicate goals and outcomes, not worrying too much about the 'how'. Eyes on, hands off.

- Minimize cognitive load for others is an important heuristic for good software development.

- Define team APIs that include code, documentation and user experience - helping other teams understand how to interact with us 






