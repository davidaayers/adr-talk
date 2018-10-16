Goal
----
Talk should be: 5-8 min = 600-960 words

The Problem
-----------

- Have you ever looked at something and said, why did we do that?
	I know every developer has faced this at some point. You're looking at something that was done (maybe you did it!), and you're not sure why it was done that way.

- As technologists, we make important architectural decisions every day
	These decisions can range from far reaching (Angular vs. React) to mundane (Infinite scroll vs. pagination for search results)
	These decisions can be made by one person, or made by the team

- Most of us do a great job and carefully thinking through these decisions:
	Taking into account all of the pros and cons of the many different options
	Discussing these options with the team
	Perhaps doing a spike or a "pepsi challenge" to determine a "best fit" for a particular decision
	And then we go about implementing it
		Maybe we update a user story with some of the information that led to the decision (usually not though)
	And all of that context is lost

- Why does that context matter?
	Without it, people have two choices when faced with a decision point:
		Blindly trust the original decision
			Which might be ok, if it was the right decision in the first place that carefully considered the consequences
		Or, Blindly change it
			Which might also be ok, but without understanding the motivation or consequences (THE CONTEXT) of the original decision, or some crucial non-functional requirement, it might cause damage to the project and/or the team

The Solution
------------

- ADR: Architecture decision records

- Lightweight, text based solution, usually written in Markdown
	Markdown allows "pretty" rendering when used with Github, Gitlab & others, still human readable

- ADRs are saved *with* the project
	Create a top-level `adr` directory	

- One ADR per file, saved with an incrememting sequence, for example:
	0001-git-for-version-control.md

- Anatomy of an ADR
	Title
		Titles are usually best expressed as simple noun phrases:
			"Git for version control"
			"LDAP for authentication"
			"Spring MVC for web development"
	Status
		One of
			Proposed
			Accepted
			Superseded
			Deprecated

			Side note: The original idea around ADRs was that they were immutable.
			This is one area where, in the past, we have deviated from the original ideas around ADRs. For superseded & deprecated ADRs, we either just changed the ADR itself, or moved it to an "archive" directory, to reduce the signal-to-noise ratio. In my opinion, changing ADRs is fine, you are storing them in source control, after all, so you don't lose any context if they change over time.

	Context
		Describes the forces at play, in a factual way. These forces can be technology-based, politically-based, culturally-based, project-based, etc. There is likely tension, and if so, the context should reflect that tension in a non-biased way.

	Decision
		Most commonly stated as "We will..." and then the decision, or just a statement of the decision itself.

	Consequences
		Every decision has consequences, for good or ill. Record them here. Again, pay attention to the language used; these aren't value judgements, they are statements of fact, or as close as you can get.

- Short and to the point
	No more than one or two pages

- Use PR/MR Workflow
	Leverage the workflow you're probably already using; new ADRs can be proposed by submitting a Pull Request, and any discussion related to what goes into the ADR itself is captured as part of the repo in Github/Gitlab/etc.

- Tools:
	Command line ADR tool: https://github.com/npryce/adr-tools
	Compendium of ADR information: https://adr.github.io/

- Don't sweat the details — if you’re not sure if you should create an ADR, create one. 
	* Can be as simple as choice of IDE (eclipse vs. IntelliJ)
    * Or as complex as documenting a spike done to validate an architectural approach
    * Can also document feature decisions: Infinite scroll vs. pagination

- What about overarching concerns that apply to more than one project
	We created a single gihub repo called "Technical Architecture", and it contained an _adr_ directory for these types of organizational/deparmental decisions. Other stuff, like architectural diagrams were also stored there [PlantUML](http://plantuml.com/) is a good tool for text-based architecture diagrams.

- What about wikis?
	Lots of people use wikis to try to document these types of decisions, which is better than nothing
	But, there is a disconnect (usually) between the code and the wiki, and in most placed, wikis are where documents go to die


The Benefits
------------

- New people joining the team can better understand the thought processes that lead to current state

- Stops people from repeating the sins of the past
    How many times have we said "I swear we looked at that, but I don’t really remember"

- Informs current decision making processes - by looking at all of the decisions that were made in a project, one can get a sense for the types of decisions that are made, which in itself is informative and provides context

- Real world examples:
	https://github.com/npryce/adr-tools/tree/master/doc/adr
	https://github.com/arachne-framework/architecture
	https://github.com/marc-bouvier/trello2eisenhower/tree/master/adr
	https://github.com/hilton/scripting-docs/tree/master/ADR

- ADRs = Goodness!

- Recommended by ThoughtWorks Technology Radar
	https://www.thoughtworks.com/radar/techniques



