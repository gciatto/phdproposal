# DOCTORAL PROJECT DRAFT

## Brainstorming

* Interaction space is orthogonal w.r.t. computations

* Nowadays systems are complex, i.e. their dynamics is unpredictable

* We need a means to govern the interaction space that should be:
  * De-centralized, i.e. there exists no global view on a system, no single point of failure, only local interaction are allowed, algorithms are distributed and decentralized;
    * By "decentralization" I refer to a notion similar to the one of Filed Calculus, where actual devices disappear and the focus is on the system working as an single "aggregate" machine only leveraging on decentralized algorithms build on top of a core set of primitives and assumptions.
  * Scalable w.r.t. the amount of participants joining them;
    * Scalability should not rely (only) on the capability of allocating more computational resources for the systems, but on decentralization, too.
  * Self-organizing, i.e. they should learn from their own dynamic behavior, from their interaction with users and the environment(s) they are situated into.
  * Easy to design and implement, i.e. they should rely on a limited set of general purpose mechanisms which can be used to build more complex capabilities,
  so it is important to both define such fine-grained mechanisms and to actually build more coarse-grained capabilities matching the need of real-world applications.
  This also implies the easy to learn/use/extend languages and tools should be developed enabling developers to easily designing/testing/observing/debugging the interaction space.

* Cite Tucson, Respect and Mok as conceptual frameworks having some of the desires features but still missing something.
  * For instance, even if Tucson allows multiple nodes & TCs to be instantiated, most of the interesting things happen within individual TCs thus preventing a real decentralization.
  I would prefer the coordination medium to be a totally decentralized, maybe composed by the aggregation/cooperation of several TCs interconnected by a network structure (essentially a distributed hash-map + suspensive & generative semantics + reactions + spreading facilities).

  * Respect is like an assembly for the interaction space: theoretically general-purpose, pragmatically unusable.

          Finire sta frase
          The transactional semantics is maybe a too-tight constraint. Generative semantics is sufficient IMWO: whenever a

* Cite and introduce MAS, WfMS and their binding with (stigmergic) coordination.
  * In MAS, coordination means governing the interaction space, i.e. providing a way for agents to interact in an uncoupled manner
  * In WfMS, coordination means ordering the activities composing one or more processes, i.e. providing a way to specify a partial order for activities thus dictating which ones can run in parallel.
  * Both explicitly or implicitly rely on the "event" concept and its declinations (ev. source, ev. notification, ev. occurrence, ev. type, ev. observation).
    * Sadly, the term "event" often comes with some ambiguity due to the fact that it may refer to (slightly) different things in different contexts, at different abstraction levels.
    * In MAS, agents activities or environment changes are the two only sources of events.
    * In WfMS, events are what wire activities together: they are employed to handle activity beginning, termination, suspension, resume, scheduling as well as the occurrence of unexpected situations
    * I believe that a clarification effort is needed when it comes to mix stigmergic coordination with event: which is the definition of "event"? how is it generated? what information can be observed by receivers? how do events propagate? how to mix events with generative semantics? should coordinables be aware of events?

  * So, MAS and WfMS have a lot in common and such similarities have already emerged into the litterature (Ricci Denti Omicini)
    * Sadly, this research line was not fully developed (?)

* Process mining is another promising research direction. It essentially consists of a (possibly distributed) system recognizing which processes its organization is employing by analyzing its own event logs (offline mode) or by intercepting and inspecting the events flowing trough it.
  * Process mining produces some (possibly formal) model of a process (e.g. petri-net or activity diagram) which can then be exploited by a WfMS to e.g. govern/facilitate/enrich/validate the execution of that process
  * Process mining can also be used to improve/modify/evolve existing process models making them adhere to the real-world processes they are representing.
  * I argue that (online) process mining could be integrated with coordination models making them able to (i) adapt the interaction rules to the agents/user/coordinables needs (which may mutate as time progresses), (ii) detect anomalies or provide predictions about the currently executed processes, (iii) provide recommendations when multiple activities could be executed taking into account the experience accumulated about the past events.

* Missing infrastructure
  * The need for standard communication protocol adoption

* Missing development/debugging/user-aid tools
