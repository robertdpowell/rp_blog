---
layout: fullpost
title: Team Topologies
summary: 'An effective, modern organisation building and running software is a product of the interactions between teams'
series: notes
published: true
---

##### Links

Create your own Team Topologies model --> [here](https://app.diagrams.net/?splash=0&ui=min&clibs=Uhttps%3A%2f%2fraw.githubusercontent.com%2fTeamTopologies%2fTeam-Shape-Templates%2fmaster%2fdiagrams.net%2fTeamTopologies.xml)


##### Foreword

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

- Reverse Conway - our architecture is a reflection of the communication patterns of our org. So, if we want a different architecture, design teams and interaction patternd to match the intended architecture. DBA example.

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

- API-based, separation of concerns between teams. Try not to share code bases between teams. 

- Office design an important consideration for communication flow.

- "you start seeing things from other people's viewpoints when you sit with them."


##### Chapter 4 - Static Team Topologies

- We need consciously designed team structures - team topologies. We need to explicity design our organisation to meet our goals. Don't just copy the Spotify model.

- Question we should ask ourselves: Given our skills, constraints, maturity, desired architecture and business goals, which team topology will help us deliver results faster and safer? How can we reduce or avoid handovers between teams?

- Older organisational models - functional silos, heavy outsourcing, repeated hand offs between teams.

- We want our software development teams to be set up for fast flow, minimal hand-offs and rich operational feedback flowing directly to the team. 

- Accelerate - "We must ensure delivery teams are cross-functional with all the skills necessary to design, develop, test, deploy and operate the system on the same team."

- There is no one right topology for any organisation, but many wrong ones.

- Feature teams. Product Teams.

- Being dependent on other teams to get your work done is bad because other team's have their own priorities and it is difficult to synchronise priorities across teams.

- Key for teams remaining autonomous is for external dependencies to be non-blocking. Self-service capabilites accessible on demand (easily consumable, platform-oriented), is often how this is done.

- Avoid hard dependencies with functional teams like infra and QA.

- Example - cloud team might own the provisioning process to ensure controls are in place, but product team should be able to provision the resource themselves.

- Organisation size (or software scale) and engineering maturity should influence which topologies are chosen.

- Before throwing more people at existing teams, consider instead which dependencies we want to break between existing teams.

- Look at knowledge, task and resource dependencies between teams and identify where they can be reduced.

-  We need an evolutionary path from where we are now, to where we want to be to realise organisational expectations.

- From DevOps team to 'DevOps Evangelist Team'. Get the team to own the automation themeselves.

- Don't make your DevOps team a dependency - focus on building self-service tools.


##### Chapter 5 - Four Fundamental Team Topologies

- Reduce number of team variations. We could focus on just four to reduce ambiguity (Jiao Luo)

- Combine these four with effective software boundaries and team interactions.

- There is no ops team - there is no live operation.

###### Stream-Aligned teams

- Aligned to single valuable stream of work (product, service, user journey..)

- The primary team type. All other teams are there to reduce the burden on the stream-aligned teams.

- Most teams will be stream-aligned. Ratio of 6:1 or 9:1

- They are close to customers and close to prod. They monitor in prod.

- Team is funded in a long-term sustainable manner.

- "You build it, you run it" - Werner Vogels, CTO Amazon

- Team ideally contains some generalists and some specialists. Specialists means bottlenecks!

- We use the term 'stream' as a stream should flow unimpeded. It is a more widely applicable term than 'product' or 'feature'.

- Minimal hand-offs to other teams.

###### Enabling teams

- Composed of specialists in a domain

- Have bandwidth to research and make suggestions on tooling, frameworks, practices in response to the challenges being experienced by the stream aligned teams.

- 'Technical Consulting Teams'.

- Bring solutions to problems being experienced by stream aligned teams.

- Not a permanent dependency but support for a focused, temporary period.

- Areas of speciliasm might be continuous delivery, test automation, containerisation, where the enabling team sets up a walking skeleton of a pipeline or test framework.













- Stays ahead of the curve in their area of expertise

- 'Engineering enablement'

###### Complicated sub-system teams

- Build and maintain part of system that requires specialist knowledge but is needed by many of the stream teams.

- Only expect a few.

- Work by the sub-system team should be delivered in line with the needs of the stream teams.

###### Platform teams

- Delivers internal services to reduce cognitive load on stream teams.

- Evan Bottcher definition

- Thick platform vs thin platform.

- Examples - server provisioning, access management and security enforcement.

- 'Platform as a product.'

- Possible to have inner topologies within a platform team.

- Need to focus on UX and DevEx.

- Need a feeback loop.

- Product roadmap driven by personas.




###### Avoiding Silos

- We should avoid dedicated teams of specialists as it creates hand-offs that disrupt flow.

- Instead create cross-functional stream-aligned teams supported by the other topologies.



###### Conversions

- Infrastructure teams to Platform Teams

- Component teams to Platform or other.

- Tool teams to Enabling teams.

- Support teams per stream/area.

- Architects to part-time enabling team. Supporting and enabling, not dictating.



##### Chapter 6 - Chose Team First Boundaries

- Need to find suitable team boundaries to encourage flow

- Align ownership of software to capabilities of a single team.

- Many problems come from unclear boundaries between teams.

- We don't want a 'distributed monolith'.

- 'JOINED AT THE DATABASE MONOLITH' 

- Use service mocks to test and deploy independent APIs in isolation

- Enforcing standardization leads to less experimentation and learning.

- Colocate by purpose, not just colocate bodies.

- Look for fracture planes in our software - natural split points to break up the monolith and support team autonomy

- Could align software with business domains - see DDD. Align biz and tech on terminology.

- Could split based on regulatory needs.

- Could split by change cadence allows teams moving at different speeds to not be impeded by each other.

- Could split by team location (efficiency of communication)

- Could split by risk profile.

- Could split by perfomance isolation need.

- Could split by tech (not advised, but maybe needed with a legacy app which cannot work with modern tools)

- Could split by persona (teams managing features needed by a certain persona)

- "Could we consume or provide this subsystem as a service?"


##### Chapter 7 - Team Interaction Modes

- Collaboration or X-as-a-Service or Facilitation

- Want to avoid that all teams need to communicate with each other. Intermittent communication is best.

- Provides clarity for teams.

- Key point is to choose between two teams collaborating and one team consuming something as a service from another team.

- **Collaboration** - (two teams working closely together) needed when needing to pool skillsets of more than one team, perhaps when exploring a new innovation or technology and discovery/rapid learning needed.

- A need for ongoing collaboration indicates incorrect team boundaries or skill mix

- Collaboration comes at a cost and needs tangible rewards. 'Collaboration tax'.

- Collaboration mode should be activated with only one other team at a time.

- *High trust and mutual collaboration*

- **X-as-a-service** - 'when it needs to just work'

- Clean API and/or boundary between teams.

- DevEx should be highly compelling

- Less innovation possiblity than Collaboration mode, as API/interface clearly defined and locked down.

- *Emphasise the user experience*

- *Needs people with strong product and service management expertise*

- **Facilitating** - main mode of an enabling team.

- Help ensure the quality of interactions across teams is good.

- Promise theory - Mark Burgess.

- *Help and be helped*

- *needs people with strong mentoring and facilitating experience*

- Collaborate on ambiguous interfaces until they are proven and stable.

- Role of architects to help define these boundaries as interfaces.

##### Chapter 8 - Evolve Team Structures with Organisational Sensing

- **The deliberate change in team interaction to enhance delivery capability is the essence of strategic technology leadership**

- Key point - team topologies should evolve and we can set target states we aim to achieve with a plan to get there, learning as we go.

- Typical evolution pattern - Collab(discovery)-->Limited Collab --> X-as-a-service (predictable delivery).

- How do we know when to evolve?

- *software or domain too large for team, leads to individuals on the team becoming specialists in certain products and then single points of failure/bottlenecks*

- *delivery cadence is slowing down*

- *many teams rely on large set of underlying services*

- We need telemetry to sense when things are not going well

- **Treat Ops as an input to dev**

- Keep ops at least aligned to the same value stream as dev.

- Separate maintenance/BAU teams work against reponsiveness.

##### Chapter 8 - Next Generation Digital Operating Model

- The 4 team types is all that is needed.

- The team is the fundamental unit of delivery.

- Switch from technology first to team/communication first approach to org design.

- Team structures must match the required system architecture.

- How to get started:-
- Start with the team
- Identify streams of change that will be supported by all other teams
- Identify a TVP
- Identify gaps in non tech requirements (coaching, mentoring, service management, documentation). Not just about technologists.
- Explain it to people! Team first approach, Conway's law, interaction models.
