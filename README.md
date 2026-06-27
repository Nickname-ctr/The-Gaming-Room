# Cplusplus-Program-v2

This repository holds the completed software design document for The Gaming Room, a client that wanted to expand their Android drawing game, Draw It or Lose It, into a web-based app that works on any device. The document covers requirements, design constraints, a UML domain model, a platform evaluation, and architecture recommendations.

**Briefly summarize The Gaming Room client and their software requirements. Who was the client? What type of software did they want you to design?**

The Gaming Room had a drawing game that only ran on Android and wanted it accessible in a browser on any device, including Windows, macOS, Linux, iOS, and Android. The main requirements were that a game could hold one or more teams, each team could hold multiple players, and all game and team names had to be unique. On the technical side, only one instance of the game could exist in memory at a time, enforced at the software design level.

**What did you do particularly well in developing this documentation?**

The Design Constraints section worked well. Each constraint explains the problem, the pattern that solves it, and what would go wrong without it rather than just naming the pattern. The Domain Model section does the same, walking through each UML class and connecting every decision back to a specific client requirement.

**What about the process of working through a design document did you find helpful when developing the code?**

Having the document done first meant the class structure was clear before any code was written. Knowing Game, Team, and Player all shared an id and name made the abstract Entity base class an obvious choice up front rather than a fix added later. It also worked as a reference while coding, making it easier to stay consistent and avoid revisiting decisions that had already been settled.

**If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?**

The platform evaluation section is what I would go back and revise. It covers the major operating systems and makes a server recommendation, but it does not go into much detail on mobile browsers specifically, which matters given that the client was moving from an Android app. Adding a closer look at how the game would behave on a mobile browser, including touch input and screen size differences, would have made the recommendation more complete and more useful to the development team.

**How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?**

The client's requirements were read as rules about what the system had to allow and prevent, not just a feature list. "Only one game instance" is a consistency rule, and reading it that way pointed directly to the Singleton pattern. Getting user needs right in the design phase matters because fixing a missed requirement after the system is built takes a lot more time and effort.

**How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?**

The process started with the requirements, identifying what the system had to do and what it had to prevent, then matching each constraint to an existing design pattern. In the future, writing requirements in a numbered and testable format early on would make it easier to confirm every design decision has a clear reason behind it. For a distributed system specifically, catching shared-state problems in the design phase means the storage solution gets built in from the start rather than added as a fix later.
