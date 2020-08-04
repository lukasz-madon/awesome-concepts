# Awesome Concepts  [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

Awesome list about all kinds of interesting topics: Laws, Principles, Mental Models, Cognitive Biases


*To contribute, click README.md and then the pencil icon. Make your changes and click the "Propose file change" button to submit a pull request. Make sure to follow [the contributions guidelines](CONTRIBUTING.md).*


<!-- MarkdownTOC depth=4 -->

  - [Laws](#laws)
    - [Amdahl's Law](#amdahls-law)
    - [The Broken Windows Theory](#the-broken-windows-theory)
    - [Brooks' Law](#brooks-law)
    - [Conway's Law](#conways-law)
    - [Cunningham's Law](#cunninghams-law)
    - [Dunbar's Number](#dunbars-number)
    - [Gall's Law](#galls-law)
    - [Goodhart's Law](#goodharts-law)
    - [Hanlon's Razor](#hanlons-razor)
    - [Hofstadter's Law](#hofstadters-law)
    - [Hutber's Law](#hutbers-law)
    - [The Hype Cycle & Amara's Law](#the-hype-cycle--amaras-law)
    - [Hyrum's Law (The Law of Implicit Interfaces)](#hyrums-law-the-law-of-implicit-interfaces)
    - [Kernighan's Law](#kernighans-law)
    - [Metcalfe's Law](#metcalfes-law)
    - [Moore's Law](#moores-law)
    - [Murphy's Law / Sod's Law](#murphys-law--sods-law)
    - [Occam's Razor](#occams-razor)
    - [Parkinson's Law](#parkinsons-law)
    - [Premature Optimization Effect](#premature-optimization-effect)
    - [Putt's Law](#putts-law)
    - [Reed's Law](#reeds-law)
    - [The Law of Conservation of Complexity (Tesler's Law)](#the-law-of-conservation-of-complexity-teslers-law)
    - [The Law of Leaky Abstractions](#the-law-of-leaky-abstractions)
    - [The Law of Triviality](#the-law-of-triviality)
    - [The Unix Philosophy](#the-unix-philosophy)
    - [The Spotify Model](#the-spotify-model)
    - [Wadler's Law](#wadlers-law)
    - [Wheaton's Law](#wheatons-law)
  - [Principles](#principles)
    - [The Dilbert Principle](#the-dilbert-principle)
    - [The Pareto Principle (The 80/20 Rule)](#the-pareto-principle-the-8020-rule)
    - [The Peter Principle](#the-peter-principle)
    - [The Robustness Principle (Postel's Law)](#the-robustness-principle-postels-law)
    - [SOLID](#solid)
    - [The Single Responsibility Principle](#the-single-responsibility-principle)
    - [The Open/Closed Principle](#the-openclosed-principle)
    - [The Liskov Substitution Principle](#the-liskov-substitution-principle)
    - [The Interface Segregation Principle](#the-interface-segregation-principle)
    - [The Dependency Inversion Principle](#the-dependency-inversion-principle)
    - [The DRY Principle](#the-dry-principle)
    - [The KISS principle](#the-kiss-principle)
    - [YAGNI](#yagni)
    - [The Fallacies of Distributed Computing](#the-fallacies-of-distributed-computing)
  - [Mental Models](#mental-models)
  - [Cognitive Biases](#cognitive-biases)
  - [UX Laws](#ux-laws)
  - [Books](#books)


<!-- /MarkdownTOC -->


## Laws

### Amdahl's Law

[Amdahl's Law on Wikipedia](https://en.wikipedia.org/wiki/Amdahl%27s_law)

> Amdahl's Law is a formula which shows the _potential speedup_ of a computational task which can be achieved by increasing the resources of a system. Normally used in parallel computing, it can predict the actual benefit of increasing the number of processors, which is limited by the parallelisability of the program.

Best illustrated with an example. If a program is made up of two parts, part A, which must be executed by a single processor, and part B, which can be parallelised, then we see that adding multiple processors to the system executing the program can only have a limited benefit. It can potentially greatly improve the speed of part B - but the speed of part A will remain unchanged.

The diagram below shows some examples of potential improvements in speed:

<img width="480px" alt="Diagram: Amdahl's Law" src="./images/amdahls_law.png" />

*(Image Reference: By Daniels220 at English Wikipedia, Creative Commons Attribution-Share Alike 3.0 Unported, https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg)*

As can be seen, even a program which is 50% parallelisable will benefit very little beyond 10 processing units, whereas a program which is 95% parallelisable can still achieve significant speed improvements with over a thousand processing units.

As [Moore's Law](#moores-law) slows, and the acceleration of individual processor speed slows, parallelisation is key to improving performance. Graphics programming is an excellent example - with modern Shader based computing, individual pixels or fragments can be rendered in parallel - this is why modern graphics cards often have many thousands of processing cores (GPUs or Shader Units).

See also:

- [Brooks' Law](#brooks-law)
- [Moore's Law](#moores-law)

### The Broken Windows Theory

[The Broken Windows Theory on Wikipedia](https://en.wikipedia.org/wiki/Broken_windows_theory)

The Broken Windows Theory suggests that visible signs of crime (or lack of care of an environment) lead to further and more serious crimes (or further deterioration of the environment).

This theory has been applied to software development, suggesting that poor quality code (or [Technical Debt](#TODO)) can lead to a perception that efforts to improve quality may be ignored or undervalued, thus leading to further poor quality code. This effect cascades leading to a great decrease in quality over time.

See also:

- [Technical Debt](#TODO)

Examples:

- [The Pragmatic Programming: Software Entropy](https://pragprog.com/the-pragmatic-programmer/extracts/software-entropy)
- [Coding Horror: The Broken Window Theory](https://blog.codinghorror.com/the-broken-window-theory/)
- [OpenSource: Joy of Programming - The Broken Window Theory](https://opensourceforu.com/2011/05/joy-of-programming-broken-window-theory/)

### Brooks' Law

[Brooks' Law on Wikipedia](https://en.wikipedia.org/wiki/Brooks%27s_law)

> Adding human resources to a late software development project makes it later.

This law suggests that in many cases, attempting to accelerate the delivery of a project which is already late, by adding more people, will make the delivery even later. Brooks is clear that this is an over-simplification, however, the general reasoning is that given the ramp up time of new resources and the communication overheads, in the immediate short-term velocity decreases. Also, many tasks may not be divisible, i.e. easily distributed between more resources, meaning the potential velocity increase is also lower.

The common phrase in delivery "Nine women can't make a baby in one month" relates to Brooks' Law, in particular, the fact that some kinds of work are not divisible or parallelisable.

This is a central theme of the book '[The Mythical Man Month](#reading-list)'.

See also:

- [Death March](#todo)
- [Reading List: The Mythical Man Month](#reading-list)

### Conway's Law

[Conway's Law on Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_law)

This law suggests that the technical boundaries of a system will reflect the structure of the organisation. It is commonly referred to when looking at organisation improvements, Conway's Law suggests that if an organisation is structured into many small, disconnected units, the software it produces will be. If an organisation is built more around 'verticals' which are orientated around features or services, the software systems will also reflect this.

See also:

- [The Spotify Model](#the-spotify-model)

### Cunningham's Law

[Cunningham's Law on Wikipedia](https://en.wikipedia.org/wiki/Ward_Cunningham#Cunningham's_Law)

> The best way to get the right answer on the Internet is not to ask a question, it's to post the wrong answer.

According to Steven McGeady, Ward Cunningham advised him in the early 1980s: "The best way to get the right answer on the Internet is not to ask a question, it's to post the wrong answer." McGeady dubbed this Cunningham's law, though Cunningham denies ownership calling it a "misquote." Although originally referring to interactions on Usenet, the law has been used to describe how other online communities work (e.g., Wikipedia, Reddit, Twitter, Facebook).

See also:

- [XKCD 386: "Duty Calls"](https://xkcd.com/386/)

### Dunbar's Number

[Dunbar's Number on Wikipedia](https://en.wikipedia.org/wiki/Dunbar%27s_number)

"Dunbar's number is a suggested cognitive limit to the number of people with whom one can maintain stable social relationships— relationships in which an individual knows who each person is and how each person relates to every other person." There is some disagreement to the exact number. "... [Dunbar] proposed that humans can comfortably maintain only 150 stable relationships." He put the number into a more social context, "the number of people you would not feel embarrassed about joining uninvited for a drink if you happened to bump into them in a bar." Estimates for the number generally lay between 100 and 250.

Like stable relationships between individuals, a developer's relationship with a codebase takes effort to maintain. When faced with large complicated projects, or ownership of many projects we lean on convention, policy, and modeled procedure to scale. Dunbar's number is not only important to keep in mind as an office grows, but also when setting the scope for team efforts or deciding when a system should invest in tooling to assist in modeling and automating logistical overhead. Putting the number into an engineering context, it is the number of projects (or normalized complexity of a single project) for which you would feel confident in joining an on-call rotation to support.

See also:

- [Conway's Law](#conways-law)

### Gall's Law

[Gall's Law on Wikipedia](https://en.wikipedia.org/wiki/John_Gall_(author)#Gall's_law)

> A complex system that works is invariably found to have evolved from a simple system that worked. A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over with a working simple system.
>
> ([John Gall](https://en.wikipedia.org/wiki/John_Gall_(author)))

Gall's Law implies that attempts to _design_ highly complex systems are likely to fail. Highly complex systems are rarely built in one go, but evolve instead from more simple systems.

The classic example is the world-wide-web. In its current state, it is a highly complex system. However, it was defined initially as a simple way to share content between academic institutions. It was very successful in meeting these goals and evolved to become more complex over time.

See also:

- [KISS (Keep It Simple, Stupid)](#the-kiss-principle)

### Goodhart's Law

[The Goodhart's Law on Wikipedia](https://en.wikipedia.org/wiki/Goodhart's_law)

> Any observed statistical regularity will tend to collapse once pressure is placed upon it for control purposes.
>
> _Charles Goodhart_

Also commonly referenced as:

> When a measure becomes a target, it ceases to be a good measure.
>
> _Marilyn Strathern_

The law states that the measure-driven optimizations could lead to devaluation of the measurement outcome itself. Overly selective set of measures ([KPIs](https://en.wikipedia.org/wiki/Performance_indicator)) blindly applied to a process results in distorted effect. People tend to optimize locally by "gaming" the system in order to satisfy particular metrics instead of paying attention to holistic outcome of their actions.

Real-world examples:
- Assert-free tests satisfy the code coverage expectation, despite the fact that the metric intent was to create well-tested software.
- Developer performance score indicated by the number of lines committed leads to unjustifiably bloated codebase.

See also:
- [Goodhart’s Law: How Measuring The Wrong Things Drive Immoral Behaviour](https://coffeeandjunk.com/goodharts-campbells-law/)
- [Dilbert on bug-free software](https://dilbert.com/strip/1995-11-13)

### Hanlon's Razor

[Hanlon's Razor on Wikipedia](https://en.wikipedia.org/wiki/Hanlon%27s_razor)

> Never attribute to malice that which is adequately explained by stupidity.
>
> Robert J. Hanlon

This principle suggests that actions resulting in a negative outcome were not a result of ill will. Instead the negative outcome is more likely attributed to those actions and/or the impact being not fully understood.

### Hofstadter's Law

[Hofstadter's Law on Wikipedia](https://en.wikipedia.org/wiki/Hofstadter%27s_law)

> It always takes longer than you expect, even when you take into account Hofstadter's Law.
>
> (Douglas Hofstadter)

You might hear this law referred to when looking at estimates for how long something will take. It seems a truism in software development that we tend to not be very good at accurately estimating how long something will take to deliver.

This is from the book '[Gödel, Escher, Bach: An Eternal Golden Braid](#reading-list)'.

See also:

- [Reading List: Gödel, Escher, Bach: An Eternal Golden Braid](#reading-list)

### Hutber's Law

[Hutber's Law on Wikipedia](https://en.wikipedia.org/wiki/Hutber%27s_law)

> Improvement means deterioration.
>
> ([Patrick Hutber](https://en.wikipedia.org/wiki/Patrick_Hutber))

This law suggests that improvements to a system will lead to deterioration in other parts, or it will hide other deterioration, leading overall to a degradation from the current state of the system.

For example, a decrease in response latency for a particular end-point could cause increased throughput and capacity issues further along in a request flow, affecting an entirely different sub-system.

### The Hype Cycle & Amara's Law

[The Hype Cycle on Wikipedia](https://en.wikipedia.org/wiki/Hype_cycle)

> We tend to overestimate the effect of a technology in the short run and underestimate the effect in the long run.
>
> (Roy Amara)

The Hype Cycle is a visual representation of the excitement and development of technology over time, originally produced by Gartner. It is best shown with a visual:

![The Hype Cycle](./images/gartner_hype_cycle.png)

*(Image Reference: By Jeremykemp at English Wikipedia, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=10547051)*

In short, this cycle suggests that there is typically a burst of excitement around new technology and its potential impact. Teams often jump into these technologies quickly, and sometimes find themselves disappointed with the results. This might be because the technology is not yet mature enough, or real-world applications are not yet fully realised. After a certain amount of time, the capabilities of the technology increase and practical opportunities to use it increase, and teams can finally become productive. Roy Amara's quote sums this up most succinctly - "We tend to overestimate the effect of a technology in the short run and underestimate in the long run".

### Hyrum's Law (The Law of Implicit Interfaces)

[Hyrum's Law Online](http://www.hyrumslaw.com/)

> With a sufficient number of users of an API,
> it does not matter what you promise in the contract:
> all observable behaviours of your system
> will be depended on by somebody.
>
> (Hyrum Wright)

Hyrum's Law states that when you have a _large enough number of consumers_ of an API, all behaviours of the API (even those not defined as part of a public contract) will eventually come to be depended on by someone. A trivial example may be non-functional elements such as the response time of an API. A more subtle example might be consumers who are relying on applying a regex to an error message to determine the *type* of error of an API. Even if the public contract of the API states nothing about the contents of the message, indicating users should use an associated error code, _some_ users may use the message, and changing the message essentially breaks the API for those users.

See also:

- [The Law of Leaky Abstractions](#the-law-of-leaky-abstractions)
- [XKCD 1172](https://xkcd.com/1172/)

### Kernighan's Law

> Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it.
>
> (Brian Kernighan)

Kernighan's Law is named for [Brian Kernighan](https://en.wikipedia.org/wiki/Brian_Kernighan) and derived from a quote from Kernighan and Plauger's book [The Elements of Programming Style](https://en.wikipedia.org/wiki/The_Elements_of_Programming_Style):

> Everyone knows that debugging is twice as hard as writing a program in the first place. So if you're as clever as you can be when you write it, how will you ever debug it?

While hyperbolic, Kernighan's Law makes the argument that simple code is to be preferred over complex code, because debugging any issues that arise in complex code may be costly or even infeasible.

See also:

- [The KISS Principle](#the-kiss-principle)
- [The Unix Philosophy](#the-unix-philosophy)
- [Occam's Razor](#occams-razor)

### Metcalfe's Law

[Metcalfe's Law on Wikipedia](https://en.wikipedia.org/wiki/Metcalfe's_law)

> In network theory, the value of a system grows as approximately the square of the number of users of the system.

This law is based on the number of possible pairwise connections within a system and is closely related to [Reed's Law](#reeds-law). Odlyzko and others have argued that both Reed's Law and Metcalfe's Law overstate the value of the system by not accounting for the limits of human cognition on network effects; see [Dunbar's Number](#dunbars-number).

See also:
- [Reed's Law](#reeds-law)
- [Dunbar's Number](#dunbars-number)

### Moore's Law

[Moore's Law on Wikipedia](https://en.wikipedia.org/wiki/Moore%27s_law)

> The number of transistors in an integrated circuit doubles approximately every two years.

Often used to illustrate the sheer speed at which semiconductor and chip technology has improved, Moore's prediction has proven to be highly accurate over from the 1970s to the late 2000s. In more recent years, the trend has changed slightly, partly due to [physical limitations on the degree to which components can be miniaturised](https://en.wikipedia.org/wiki/Quantum_tunnelling). However, advancements in parallelisation, and potentially revolutionary changes in semiconductor technology and quantum computing may mean that Moore's Law could continue to hold true for decades to come.

### Murphy's Law / Sod's Law

[Murphy's Law on Wikipedia](https://en.wikipedia.org/wiki/Murphy%27s_law)

> Anything that can go wrong will go wrong.

Related to [Edward A. Murphy, Jr](https://en.wikipedia.org/wiki/Edward_A._Murphy_Jr.) _Murphy's Law_ states that if a thing can go wrong, it will go wrong.

This is a common adage among developers. Sometimes the unexpected happens when developing, testing or even in production. This can also be related to the (more common in British English) _Sod's Law_:

> If something can go wrong, it will, at the worst possible time.

These 'laws' are generally used in a comic sense. However, phenomena such as [_Confirmation Bias_](#TODO) and [_Selection Bias_](#TODO) can lead people to perhaps over-emphasise these laws (the majority of times when things work, they go unnoticed, failures however are more noticeable and draw more discussion).

See Also:

- [Confirmation Bias](#TODO)
- [Selection Bias](#TODO)

### Occam's Razor

[Occam's Razor on Wikipedia](https://en.wikipedia.org/wiki/Occam's_razor)

> Entities should not be multiplied without necessity.
>
> William of Ockham

Occam's razor says that among several possible solutions, the most likely solution is the one with the least number of concepts and assumptions. This solution is the simplest and solves only the given problem, without introducing accidental complexity and possible negative consequences.

If you have 2 competing hypotheses (two hypotheses for which the evidence supports both), you use the one with less assumptions. Partly because the one with less assumptions will be easier to work with and lead to models that are easier to understand. But mostly because less assumptions makes it easier to falsify.

See also:

- [YAGNI](#yagni)
- [No Silver Bullet: Accidental Complexity and Essential Complexity](https://en.wikipedia.org/wiki/No_Silver_Bullet)

Example:

- [Lean Software Development: Eliminate Waste](https://en.wikipedia.org/wiki/Lean_software_development#Eliminate_waste)

### Parkinson's Law

[Parkinson's Law on Wikipedia](https://en.wikipedia.org/wiki/Parkinson%27s_law)

> Work expands so as to fill the time available for its completion.

In its original context, this Law was based on studies of bureaucracies. It may be pessimistically applied to software development initiatives, the theory being that teams will be inefficient until deadlines near, then rush to complete work by the deadline, thus making the actual deadline somewhat arbitrary.

If this law were combined with [Hofstadter's Law](#hofstadters-law), an even more pessimistic viewpoint is reached - work will expand to fill the time available for its completion and *still take longer than expected*.

See also:

- [Hofstadter's Law](#hofstadters-law)

### Premature Optimization Effect

[Premature Optimization on WikiWikiWeb](http://wiki.c2.com/?PrematureOptimization)

> Premature optimization is the root of all evil.
>
> [(Donald Knuth)](https://twitter.com/realdonaldknuth?lang=en)

In Donald Knuth's paper [Structured Programming With Go To Statements](http://wiki.c2.com/?StructuredProgrammingWithGoToStatements), he wrote: "Programmers waste enormous amounts of time thinking about, or worrying about, the speed of noncritical parts of their programs, and these attempts at efficiency actually have a strong negative impact when debugging and maintenance are considered. We should forget about small efficiencies, say about 97% of the time: **premature optimization is the root of all evil**. Yet we should not pass up our opportunities in that critical 3%."

However, _Premature Optimization_ can be defined (in less loaded terms) as optimizing before we know that we need to.

### Putt's Law

[Putt's Law on Wikipedia](https://en.wikipedia.org/wiki/Putt%27s_Law_and_the_Successful_Technocrat)

> Technology is dominated by two types of people, those who understand what they do not manage and those who manage what they do not understand.

Putt's Law is often followed by Putt's Corollary:

> Every technical hierarchy, in time, develops a competence inversion.

These statements suggest that due to various selection criteria and trends in how groups organise, there will be a number of skilled people at working levels of a technical organisations, and a number of people in managerial roles who are not aware of the complexities and challenges of the work they are managing. This can be due to phenomena such as [The Peter Principle](#the-peter-principle) or [The Dilbert Principle](#the-dilbert-principle).

However, it should be stressed that Laws such as this are vast generalisations and may apply to _some_ types of organisations, and not apply to others.

See also:

- [The Peter Principle](#the-peter-principle)
- [The Dilbert Principle](#the-dilbert-principle)


### Reed's Law

[Reed's Law on Wikipedia](https://en.wikipedia.org/wiki/Reed's_law)

> The utility of large networks, particularly social networks, scales exponentially with the size of the network.

This law is based on graph theory, where the utility scales as the number of possible sub-groups, which is faster than the number of participants or the number of possible pairwise connections. Odlyzko and others have argued that Reed's Law overstates the utility of the system by not accounting for the limits of human cognition on network effects; see [Dunbar's Number](#dunbars-number).

See also:
- [Metcalfe's Law](#metcalfes-law)
- [Dunbar's Number](#dunbars-number)

### The Law of Conservation of Complexity (Tesler's Law)

[The Law of Conservation of Complexity on Wikipedia](https://en.wikipedia.org/wiki/Law_of_conservation_of_complexity)

This law states that there is a certain amount of complexity in a system which cannot be reduced.

Some complexity in a system is 'inadvertent'. It is a consequence of poor structure, mistakes, or just bad modeling of a problem to solve. Inadvertent complexity can be reduced (or eliminated). However, some complexity is 'intrinsic' as a consequence of the complexity inherent in the problem being solved. This complexity can be moved, but not eliminated.

One interesting element to this law is the suggestion that even by simplifying the entire system, the intrinsic complexity is not reduced, it is _moved to the user_, who must behave in a more complex way.

### The Law of Leaky Abstractions

[The Law of Leaky Abstractions on Joel on Software](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/)

> All non-trivial abstractions, to some degree, are leaky.
>
> ([Joel Spolsky](https://twitter.com/spolsky))

This law states that abstractions, which are generally used in computing to simplify working with complicated systems, will in certain situations 'leak' elements of the underlying system, this making the abstraction behave in an unexpected way.

An example might be loading a file and reading its contents. The file system APIs are an _abstraction_ of the lower level kernel systems, which are themselves an abstraction over the physical processes relating to changing data on a magnetic platter (or flash memory for an SSD). In most cases, the abstraction of treating a file like a stream of binary data will work. However, for a magnetic drive, reading data sequentially will be *significantly* faster than random access (due to increased overhead of page faults), but for an SSD drive, this overhead will not be present. Underlying details will need to be understood to deal with this case (for example, database index files are structured to reduce the overhead of random access), the abstraction 'leaks' implementation details the developer may need to be aware of.

The example above can become more complex when _more_ abstractions are introduced. The Linux operating system allows files to be accessed over a network but represented locally as 'normal' files. This abstraction will 'leak' if there are network failures. If a developer treats these files as 'normal' files, without considering the fact that they may be subject to network latency and failures, the solutions will be buggy.

The article describing the law suggests that an over-reliance on abstractions, combined with a poor understanding of the underlying processes, actually makes dealing with the problem at hand _more_ complex in some cases.

See also:

- [Hyrum's Law](#hyrums-law-the-law-of-implicit-interfaces)

Real-world examples:

- [Photoshop Slow Startup](https://forums.adobe.com/thread/376152) - an issue I encountered in the past. Photoshop would be slow to startup, sometimes taking minutes. It seems the issue was that on startup it reads some information about the current default printer. However, if that printer is actually a network printer, this could take an extremely long time. The _abstraction_ of a network printer being presented to the system similar to a local printer caused an issue for users in poor connectivity situations.

### The Law of Triviality

[The Law of Triviality on Wikipedia](https://en.wikipedia.org/wiki/Law_of_triviality)

This law suggests that groups will give far more time and attention to trivial or cosmetic issues rather than serious and substantial ones.

The common fictional example used is that of a committee approving plans for nuclear power plant, who spend the majority of their time discussing the structure of the bike shed, rather than the far more important design for the power plant itself. It can be difficult to give valuable input on discussions about very large, complex topics without a high degree of subject matter expertise or preparation. However, people want to be seen to be contributing valuable input. Hence a tendency to focus too much time on small details, which can be reasoned about easily, but are not necessarily of particular importance.

The fictional example above led to the usage of the term 'Bike Shedding' as an expression for wasting time on trivial details. A related term is '[Yak Shaving](https://en.wiktionary.org/wiki/yak_shaving),' which connotes a seemingly irrelevant activity that is part of a long chain of prerequisites to the main task.

### The Unix Philosophy

[The Unix Philosophy on Wikipedia](https://en.wikipedia.org/wiki/Unix_philosophy)

The Unix Philosophy is that software components should be small, and focused on doing one specific thing well. This can make it easier to build systems by composing together small, simple, well-defined units, rather than using large, complex, multi-purpose programs.

Modern practices like 'Microservice Architecture' can be thought of as an application of this law, where services are small, focused and do one specific thing, allowing complex behaviour to be composed of simple building blocks.

### The Spotify Model

[The Spotify Model on Spotify Labs](https://labs.spotify.com/2014/03/27/spotify-engineering-culture-part-1/)

The Spotify Model is an approach to team and organisation structure which has been popularised by 'Spotify'. In this model, teams are organised around features, rather than technologies.

The Spotify Model also popularises the concepts of Tribes, Guilds, Chapters, which are other components of their organisation structure.

### Wadler's Law

[Wadler's Law on wiki.haskell.org](https://wiki.haskell.org/Wadler's_Law)

> In any language design, the total time spent discussing a feature in this list is proportional to two raised to the power of its position.
>
> 0. Semantics
> 1. Syntax
> 2. Lexical syntax
> 3. Lexical syntax of comments
>
> (In short, for every hour spent on semantics, 8 hours will be spent on the syntax of comments).

Similar to [The Law of Triviality](#the-law-of-triviality), Wadler's Law states what when designing a language, the amount of time spent on language structures is disproportionately high in comparison to the importance of those features.

See also:

- [The Law of Triviality](#the-law-of-triviality)

### Wheaton's Law

[The Link](http://www.wheatonslaw.com/)

[The Official Day](https://dontbeadickday.com/)

> Don't be a dick.
>
> _Wil Wheaton_

Coined by Wil Wheaton (Star Trek: The Next Generation, The Big Bang Theory), this simple, concise, and powerful law aims for an increase in harmony and respect within a professional organization. It can be applied when speaking with coworkers, performing code reviews, countering other points of view, critiquing, and in general, most professional interactions humans have with each other.


## Principles


### The Dilbert Principle

[The Dilbert Principle on Wikipedia](https://en.wikipedia.org/wiki/Dilbert_principle)

> Companies tend to systematically promote incompetent employees to management to get them out of the workflow.
>
> _Scott Adams_

A management concept developed by Scott Adams (creator of the Dilbert comic strip), the Dilbert Principle is inspired by [The Peter Principle](#the-peter-principle). Under the Dilbert Principle, employees who were never competent are promoted to management in order to limit the damage they can do. Adams first explained the principle in a 1995 Wall Street Journal article, and expanded upon it in his 1996 business book, [The Dilbert Principle](#reading-list).

See Also:

- [The Peter Principle](#the-peter-principle)
- [Putt's Law](#putts-law)

### The Pareto Principle (The 80/20 Rule)

[The Pareto Principle on Wikipedia](https://en.wikipedia.org/wiki/Pareto_principle)

> Most things in life are not distributed evenly.

The Pareto Principle suggests that in some cases, the majority of results come from a minority of inputs:

- 80% of a certain piece of software can be written in 20% of the total allocated time (conversely, the hardest 20% of the code takes 80% of the time)
- 20% of the effort produces 80% of the result
- 20% of the work creates 80% of the revenue
- 20% of the bugs cause 80% of the crashes
- 20% of the features cause 80% of the usage

In the 1940s American-Romanian engineer Dr. Joseph Juran, who is widely credited with being the father of quality control, [began to apply the Pareto principle to quality issues](https://en.wikipedia.org/wiki/Joseph_M._Juran).

This principle is also known as: The 80/20 Rule, The Law of the Vital Few, and The Principle of Factor Sparsity.

Real-world examples:

- In 2002 Microsoft reported that by fixing the top 20% of the most-reported bugs, 80% of the related errors and crashes in windows and office would become eliminated ([Reference](https://www.crn.com/news/security/18821726/microsofts-ceo-80-20-rule-applies-to-bugs-not-just-features.htm)).

### The Peter Principle

[The Peter Principle on Wikipedia](https://en.wikipedia.org/wiki/Peter_principle)

> People in a hierarchy tend to rise to their "level of incompetence".
>
> _Laurence J. Peter_

A management concept developed by Laurence J. Peter, the Peter Principle observes that people who are good at their jobs are promoted, until they reach a level where they are no longer successful (their "level of incompetence". At this point, as they are more senior, they are less likely to be removed from the organisation (unless they perform spectacularly badly) and will continue to reside in a role which they have few intrinsic skills at, as their original skills which made them successful are not necessarily the skills required for their new jobs.

This is of particular interest to engineers - who initial start out in deeply technical roles, but often have a career path which leads to _managing_ other engineers - which requires a fundamentally different skills-set.

See Also:

- [The Dilbert Principle](#the-dilbert-principle)
- [Putt's Law](#putts-law)

### The Robustness Principle (Postel's Law)

[The Robustness Principle on Wikipedia](https://en.wikipedia.org/wiki/Robustness_principle)

> Be conservative in what you do, be liberal in what you accept from others.

Often applied in server application development, this principle states that what you send to others should be as minimal and conformant as possible, but you should aim to allow non-conformant input if it can be processed.

The goal of this principle is to build systems which are robust, as they can handle poorly formed input if the intent can still be understood. However, there are potentially security implications of accepting malformed input, particularly if the processing of such input is not well tested.

Allowing non-conformant input, in time, may undermine the ability of protocols to evolve as implementors will eventually rely on this liberality to build their features.

See Also:

- [Hyrum's Law](#hyrums-law-the-law-of-implicit-interfaces)


### SOLID

This is an acronym, which refers to:

* S: [The Single Responsibility Principle](#the-single-responsibility-principle)
* O: [The Open/Closed Principle](#the-openclosed-principle)
* L: [The Liskov Substitution Principle](#the-liskov-substitution-principle)
* I: [The Interface Segregation Principle](#the-interface-segregation-principle)
* D: [The Dependency Inversion Principle](#the-dependency-inversion-principle)

These are key principles in [Object-Oriented Programming](#todo). Design principles such as these should be able to aid developers build more maintainable systems.

### The Single Responsibility Principle

[The Single Responsibility Principle on Wikipedia](https://en.wikipedia.org/wiki/Single_responsibility_principle)

> Every module or class should have a single responsibility only.

The first of the '[SOLID](#solid)' principles. This principle suggests that modules or classes should do one thing and one thing only. In more practical terms, this means that a single, small change to a feature of a program should require a change in one component only. For example, changing how a password is validated for complexity should require a change in only one part of the program.

Theoretically, this should make the code more robust, and easier to change. Knowing that a component which is being changed has a single responsibility only means that _testing_ that change should be easier. Using the earlier example, changing the password complexity component should only be able to affect the features which relate to password complexity. It can be much more difficult to reason about the impact of a change to a component which has many responsibilities.

See also:

- [Object-Oriented Programming](#todo)
- [SOLID](#solid)

### The Open/Closed Principle

[The Open/Closed Principle on Wikipedia](https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle)

> Entities should be open for extension and closed for modification.

The second of the '[SOLID](#solid)' principles. This principle states that entities (which could be classes, modules, functions and so on) should be able to have their behaviour _extended_, but that their _existing_ behaviour should not be able to be modified.

As a hypothetical example, imagine a module which is able to turn a Markdown document into HTML. If the module could be extended to handle a newly proposed Markdown feature, without modifying the module internals, then it would be open for extension. If the module could _not_ be modified by a consumer so that now existing Markdown features are handled, then it would be _closed_ for modification.

This principle has particular relevance for object-oriented programming, where we may design objects to be easily extended, but would avoid designing objects which can have their existing behaviour changed in unexpected ways.

See also:

- [Object-Oriented Programming](#todo)
- [SOLID](#solid)

### The Liskov Substitution Principle

[The Liskov Substitution Principle on Wikipedia](https://en.wikipedia.org/wiki/Liskov_substitution_principle)

> It should be possible to replace a type with a subtype, without breaking the system.

The third of the '[SOLID](#solid)' principles. This principle states that if a component relies on a type, then it should be able to use subtypes of that type, without the system failing or having to know the details of what that subtype is.

As an example, imagine we have a method which reads an XML document from a structure which represents a file. If the method uses a base type 'file', then anything which derives from 'file' should be able to be used in the function. If 'file' supports seeking in reverse, and the XML parser uses that function, but the derived type 'network file' fails when reverse seeking is attempted, then the 'network file' would be violating the principle.

This principle has particular relevance for object-oriented programming, where type hierarchies must be modeled carefully to avoid confusing users of a system.

See also:

- [Object-Oriented Programming](#todo)
- [SOLID](#solid)

### The Interface Segregation Principle

[The Interface Segregation Principle on Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle)

> No client should be forced to depend on methods it does not use.

The fourth of the '[SOLID](#solid)' principles. This principle states that consumers of a component should not depend on functions of that component which it doesn't actually use.

As an example, imagine we have a method which reads an XML document from a structure which represents a file. It only needs to read bytes, move forwards or move backwards in the file. If this method needs to be updated because an unrelated feature of the file structure changes (such as an update to the permissions model used to represent file security), then the principle has been invalidated. It would be better for the file to implement a 'seekable-stream' interface, and for the XML reader to use that.

This principle has particular relevance for object-oriented programming, where interfaces, hierarchies and abstract types are used to [minimise the coupling](#todo) between different components. [Duck typing](#todo) is a methodology which enforces this principle by eliminating explicit interfaces.

See also:

- [Object-Oriented Programming](#todo)
- [SOLID](#solid)
- [Duck Typing](#todo)
- [Decoupling](#todo)

### The Dependency Inversion Principle

[The Dependency Inversion Principle on Wikipedia](https://en.wikipedia.org/wiki/Dependency_inversion_principle)

> High-level modules should not be dependent on low-level implementations.

The fifth of the '[SOLID](#solid)' principles. This principle states that higher level orchestrating components should not have to know the details of their dependencies.

As an example, imagine we have a program which read metadata from a website. We would assume that the main component would have to know about a component to download the webpage content, then a component which can read the metadata. If we were to take dependency inversion into account, the main component would depend only on an abstract component which can fetch byte data, and then an abstract component which would be able to read metadata from a byte stream. The main component would not know about TCP/IP, HTTP, HTML, etc.

This principle is complex, as it can seem to 'invert' the expected dependencies of a system (hence the name). In practice, it also means that a separate orchestrating component must ensure the correct implementations of abstract types are used (e.g. in the previous example, _something_ must still provide the metadata reader component a HTTP file downloader and HTML meta tag reader). This then touches on patterns such as [Inversion of Control](#todo) and [Dependency Injection](#todo).

See also:

- [Object-Oriented Programming](#todo)
- [SOLID](#solid)
- [Inversion of Control](#todo)
- [Dependency Injection](#todo)

### The DRY Principle

[The DRY Principle on Wikipedia](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

DRY is an acronym for _Don't Repeat Yourself_. This principle aims to help developers reducing the repetition of code and keep the information in a single place and was cited in 1999 by Andrew Hunt and Dave Thomas in the book [The Pragmatic Developer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

> The opposite of DRY would be _WET_ (Write Everything Twice or We Enjoy Typing).

In practice, if you have the same piece of information in two (or more) different places, you can use DRY to merge them into a single one and reuse it wherever you want/need.

See also:

- [The Pragmatic Developer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

### The KISS principle

[KISS on Wikipedia](https://en.wikipedia.org/wiki/KISS_principle)

> Keep it simple, stupid

The KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore, simplicity should be a key goal in design, and unnecessary complexity should be avoided.  Originating in the U.S. Navy in 1960, the phrase has been associated with aircraft engineer Kelly Johnson.

The principle is best exemplified by the story of Johnson handing a team of design engineers a handful of tools, with the challenge that the jet aircraft they were designing must be repairable by an average mechanic in the field under combat conditions with only these tools. Hence, the "stupid" refers to the relationship between the way things break and the sophistication of the tools available to repair them, not the capabilities of the engineers themselves. 

See also:

- [Gall's Law](#galls-law)

### YAGNI

[YAGNI on Wikipedia](https://en.wikipedia.org/wiki/You_ain%27t_gonna_need_it)

This is an acronym for _**Y**ou **A**in't **G**onna **N**eed **I**t_.

> Always implement things when you actually need them, never when you just foresee that you need them.
>
> ([Ron Jeffries](https://twitter.com/RonJeffries)) (XP co-founder and author of the book "Extreme Programming Installed")

This _Extreme Programming_ (XP) principle suggests developers should only implement functionality that is needed for the immediate requirements, and avoid attempts to predict the future by implementing functionality that might be needed later.

Adhering to this principle should reduce the amount of unused code in the codebase, and avoid time and effort being wasted on functionality that brings no value.

See also:

- [Reading List: Extreme Programming Installed](#reading-list)

### The Fallacies of Distributed Computing

[The Fallacies of Distributed Computing on Wikipedia](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)

Also known as _Fallacies of Networked Computing_, the Fallacies are a list of conjectures (or beliefs) about distributed computing, which can lead to failures in software development. The assumptions are:

- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology doesn't change
- There is one administrator
- Transport cost is zero
- The network is homogeneous

The first four items were listed by [Bill Joy](https://en.wikipedia.org/wiki/Bill_Joy) and [Tom Lyon](https://twitter.com/aka_pugs) around 1991 and first classified by [James Gosling](https://en.wikipedia.org/wiki/James_Gosling) as the "Fallacies of Networked Computing". [L. Peter Deutsch](https://en.wikipedia.org/wiki/L._Peter_Deutsch) added the 5th, 6th and 7th fallacies. In the late 90's Gosling added the 8th fallacy.

The group were inspired by what was happening at the time inside [Sun Microsystems](https://en.wikipedia.org/wiki/Sun_Microsystems).

These fallacies should be considered carefully when designing code which is resilient; assuming any of these fallacies can lead to flawed logic which fails to deal with the realities and complexities of distributed systems.


## Mental Models


### Wisdom and Circles of Competence

“Knowing what you don’t know is more useful than being brilliant.”
“Acknowledging what you don’t know is the dawning of wisdom.”

Identify your circle of competence and use your knowledge, when possible, to stay away from things you don’t understand. There are no points for difficulty at work or in life.  Avoiding stupidity is easier than seeking brilliance.

Of course this principle relates to another of Munger’s sayings: “People are trying to be smart—all I am trying to do is not to be idiotic, but it’s harder than most people think.”

And this reminds me of perhaps my favorite Mungerism of all time, the very quote that sits right beside my desk:

“It is remarkable how much long-term advantage people like us have gotten by trying to be consistently not stupid, instead of trying to be very intelligent.”

### Divergence
“Mimicking the herd invites regression to the mean.”

Here’s a simple axiom to live by: If you do what everyone else does, you’re going to get the same results that everyone else gets. This means that, taking out luck (good or bad), if you act average, you’re going to be average. If you want to move away from average, you must diverge. You must be different. And if you want to outperform others, you must be different and correct. As Munger would say, “How could it be otherwise?”

### Know When to Fold ’Em
“Life, in part, is like a poker game, wherein you have to learn to quit sometimes when holding a much-loved hand—you must learn to handle mistakes and new facts that change the odds.”

Mistakes are an opportunity to grow. How we handle adversity is up to us. This is how we become personally antifragile.

### False Models
Echoing Einstein, who said that “Not everything that counts can be counted, and not everything that can be counted counts,” Munger said this about his and Buffett’s shift to acquiring high-quality businesses for Berkshire Hathaway:

“Once we’d gotten over the hurdle of recognizing that a thing could be a bargain based on quantitative measures that would have horrified Graham, we started thinking about better businesses.”

### Being Lazy
“Sit on your ass. You’re paying less to brokers, you’re listening to less nonsense, and if it works, the tax system gives you an extra one, two, or three percentage points per annum.”

Time is a friend to a good business and the enemy of the poor business. It’s also the friend of knowledge and the enemy of the new and novel. As Seneca said, “Time discovers truth.”

### Investing Is a Perimutuel System
“You’re looking for a mispriced gamble,” says Munger. “That’s what investing is. And you have to know enough to know whether the gamble is mispriced. That’s value investing.”  At another time, he added: “You should remember that good ideas are rare— when the odds are greatly in your favor, bet heavily.”

May the odds forever be in your favor. Actually, learning properly is one way you can tilt the odds in your favor.

### Focus
When asked about his success, Munger says, “I succeeded because I have a long attention span.”

Long attention spans allow for a deep understanding of subjects. When combined with deliberate practice, focus allows you to increase your skills and get out of your rut. The Art of Focus is a divergent and correct strategy that can help you identify where the leverage points are and apply your efforts toward them.

### Fake Knowledge
“Smart people aren’t exempt from professional disasters from overconfidence.”

We’re so used to outsourcing our thinking to others that we’ve forgotten what it’s like to really understand something from all perspectives. We’ve forgotten just how much work that takes. The path of least resistance, however, is just a click away. Fake knowledge, which comes from reading headlines and skimming the news, seems harmless, but it’s not. It makes us overconfident. It’s better to remember a simple trick: anything you’re getting easily through Google or Twitter is likely to be widely known and should not be given undue weight.

However, Munger adds, “If people weren’t wrong so often, we wouldn’t be so rich.”

### Sit Quietly
Echoing Pascal, who said some version of “All of humanity’s problems stem from man’s inability to sit quietly in a room alone,” Munger adds an investing twist: “It’s waiting that helps you as an investor, and a lot of people just can’t stand to wait.”

The ability to be alone with your thoughts and turn ideas over and over, without giving in to Do Something syndrome, affects so many of us. A perfectly reasonable option is to hold your ground and await more information.

### Deal With Reality
“I think that one should recognize reality even when one doesn’t like it; indeed, especially when one doesn’t like it.”

Munger clearly learned from Joseph Tussman’s wisdom. This means facing harsh truths that you might prefer to ignore. It means meeting the world on the world’s terms, not according to how you wish it would be. If this causes temporary pain, so be it. “Your pain,” writes Kahil Gibran in The Prophet, “is the breaking of the shell that encloses your understanding.”

### Invert, always, invert

"...it is in the nature of things that many hard problems are best solved when they are addressed backward" Munger.

Instead of asking questions like "How can I make software safe" ask an inverted question "How can I make software fail?" and solve those problems.

### There Is No Free Lunch
We like quick solutions that don’t require a lot of effort. We’re drawn to the modern equivalent of an old hustler selling an all-curing tonic. However, the world does not work that way. Munger expands:

“There isn’t a single formula. You need to know a lot about business and human nature and the numbers… It is unreasonable to expect that there is a magic system that will do it for you.”

Acquiring knowledge is hard work. It’s reading and adding to your knowledge so it compounds. It’s going deep and developing fluency, something Darwin knew well.

Tne "No Free Lunch" Theorem - "No single approach can claim an inherent superiority over others, over all classes of problems" - Wolpert & McReady [1997]

### Maximization/Minimization
“In business we often find that the winning system goes almost ridiculously far in maximizing and or minimizing one or a few variables—like the discount warehouses of Costco.”

When everything is a priority, nothing is a priority. Attempting to maximize competing variables is a recipe for disaster. Picking one variable and relentlessly focusing on it, which is an effective strategy, diverges from the norm. It’s hard to compete with businesses that have correctly identified the right variables to maximize or minimize. When you focus on one variable, you’ll increase the odds that you’re quick and nimble — and can respond to changes in the terrain.

### Map and Terrain
“At Berkshire there has never been a master plan. Anyone who wanted to do it, we fired because it takes on a life of its own and doesn’t cover new reality. We want people taking into account new information.”

Plans are maps that we become attached to. Once we’ve told everyone there is a plan and what that plan is, especially multi-year plans, we’re psychologically more likely to stick to it because coming out and changing it would be admitting we were wrong. This makes it harder for us to change our strategies when we need to, so we’re stacking the odds against ourselves. Detailed five-year plans (that will clearly be wrong) are as disastrous as overly general five-year plans (which can never be wrong).

Scrap the plan, isolate the key variables that you need to maximize and minimize, and follow the agile path blazed by Henry Singleton and followed by Buffett and Munger.

### The Keys to Good Government
There are three keys: honesty, effectiveness, and efficiency. Munger says:

“In a democracy, everyone takes turns. But if you really want a lot of wisdom, it’s better to concentrate decisions and process in one person. It’s no accident that Singapore has a much better record, given where it started, than the United States. There, power was concentrated in an enormously talented person, Lee Kuan Yew, who was the Warren Buffett of Singapore.”

Lee Kuan Yew put it this way: “With few exceptions, democracy has not brought good government to new developing countries. … What Asians value may not necessarily be what Americans or Europeans value. Westerners value the freedoms and liberties of the individual. As an Asian of Chinese cultural background, my values are for a government which is honest, effective, and efficient.”

### One Step At a Time
“Spend each day trying to be a little wiser than you were when you woke up. Discharge your duties faithfully and well. Slug it out one inch at a time, day by day. At the end of the day—if you live long enough—most people get what they deserve.”

An incremental approach to life reminds one of the nature of compounding. There will always be someone going faster than you, but you can learn from the Darwinian guide to overachieving your natural IQ. In order for this approach to be effective, you need a long axis of time as well as continuous incremental progress.


### Know-it-alls
“I try to get rid of people who always confidently answer questions about which they don’t have any real knowledge.”

Few things have made as much of a difference in my life as systemically removing (and when that’s not possible, reducing the importance of) people who think they know the answer to everything.

### Stoic Resolve
“There’s no way that you can live an adequate life without many mistakes. In fact, one trick in life is to get so you can handle mistakes. Failure to handle psychological denial is a common way for people to go broke.”

While we all make mistakes, it’s how we respond to failure that defines us.


### Getting Rich
“The desire to get rich fast is pretty dangerous.”

Getting rich is a function of being happy with what you have, spending less than you make, and time.

### Thinking
“We all are learning, modifying, or destroying ideas all the time. Rapid destruction of your ideas when the time is right is one of the most valuable qualities you can acquire. You must force yourself to consider arguments on the other side.”

“It’s bad to have an opinion you’re proud of if you can’t state the arguments for the other side better than your opponents. This is a great mental discipline.”

Thinking is a lot of work. “My first thought,” William Deresiewicz said in one of my favorite speeches, “is never my best thought. My first thought is always someone else’s; it’s always what I’ve already heard about the subject, always the conventional wisdom.”


### Choose Your Associates Wisely
“Oh, it’s just so useful dealing with people you can trust and getting all the others the hell out of your life. It ought to be taught as a catechism. … [W]ise people want to avoid other people who are just total rat poison, and there are a lot of them.”

## Cognitive Biases

https://en.wikipedia.org/wiki/List_of_cognitive_biases

## UX laws

1. Aesthetic Usability Effect - Users often perceive aesthetically pleasing design as design that’s more usable.
1. Doherty Threshold - Productivity soars when a computer and its users interact at a pace (<400ms) that ensures that neither has to wait on the other.
1. Fitts’s Law - The time to acquire a target is a function of the distance to and size of the target.
1. Hick’s Law - The time it takes to make a decision increases with the number and complexity of choices.
1. Jakob’s Law - Users spend most of their time on other sites. This means that users prefer your site to work the same way as all the other sites they already know.
1. Law of Common Region - Elements tend to be perceived into groups if they are sharing an area with a clearly defined boundary.
1. Law of Prägnanz - People will perceive and interpret ambiguous or complex images as the simplest form possible, because it is the interpretation that requires the least cognitive effort of us.
1. Law of Proximity - Objects that are near, or proximate to each other, tend to be grouped together.
1. Law of Similarity - The human eye tends to perceive similar elements in a design as a complete picture, shape, or group, even if those elements are separated.
1. Law of Uniform Connectedness - Elements that are visually connected are perceived as more related than elements with no connection.
1. Miller’s Law - The average person can only keep 7 (plus or minus 2) items in their working memory.
1. Peak-End Rule - People judge an experience largely based on how they felt at its peak and at its end, rather than the total sum or average of every moment of the experience.
1. Serial Position Effect - Users have a propensity to best remember the first and last items in a series.
1. Von Restorff Effect - The Von Restorff effect, also known as The Isolation Effect, predicts that when multiple similar objects are present, the one that differs from the rest is most likely to be remembered.
1. Zeigarnik Effect - People remember uncompleted or interrupted tasks better than completed tasks.


https://lawsofux.com/

## Books

The selfish gene - for understanding human behavior

Meditations of Marcus Aurelius - for understanding how to be content

Debt, the first 5,000 years - for understanding money and finance from the ground up

Wright Brothers - for understanding how technological breakthroughs happen

Snowball (Warren Buffet), Andrew Carnegie and Rockefeller biographies - for understanding the mental mindset to win in business (it's not what you think)

Hackers and painters - for understanding startups and how/why they work

Zen and the art of motorcycle maintenance - for understanding beauty in the routine

Essentialism, the disciplined pursuit of less and Walden - for understanding how "stuff" gets in the way of happiness

Les Miserables - for understanding love

Poor Charlie's Almanac


### References

https://buffettmungerwisdom.files.wordpress.com/2013/01/mungerspeech_june_95.pdf

https://github.com/dwmkerr/hacker-laws

https://medium.com/@yegg/mental-models-i-find-repeatedly-useful-936f1cc405d

http://www.defmacro.org/2016/12/22/models.html

https://en.wikipedia.org/wiki/List_of_cognitive_biases

https://fs.blog/mental-models/
