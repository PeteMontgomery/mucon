
muCon - Microservices, DDD & Software Architecture
==================================================

Day 1
=====

Keynote - Socio-Technique and Structure.
Michael C. Feathers
------------------------------------------------------------

System design - social & technical

- *Conway's law* - systems reflect communication / teams
- Dunbar's number - 150 relationships
- Power law distribution (method length, class size, lots more) (most things tiny, a few things massive)
- Coding 'heroes' - how to prevent them destroying the team 
- Pareto distribution. (80/20 contributions tend to happen in teams and open source contrib.
  - Can we work *with* it to make it non-toxic.
 - natural consequence (small number of highly productive / )
 - is it problem? how much?
 - even when using agile? 
 - what's dangerous is what if it's the wrong person? obvious risk if they leave
 - make a project that looks like it came from one person's mind (mob programming - we already to this a little!) 
- Galileo - structure must change as we scale
- Graph theory - cliques.
- SRP falls apart as we scale - this can drive structure
- Cost of modularity is explicit complexity
- Same and fewer tools => productivity
  - (1 person, 1 tool, 1 codebase is most productive)
  - (2 people also v productive)
- Are all problems essentially scaling problems?
- Look at Spotify organistion model
- Be aware of underlying forces
- Code and social structure have limits - work with them, not against them

Microservices from Day One.
Richard Rodger
------------------------------------------
- Is it a good idea to start with microservices?
- Wrote 'The Tao of Microservice' [Manning]
- Javascript being crappy pushed towards microservices to stay sane
- Standard enterprise project built with muServices first
- "Most people are using React" for front end but they used Vue
- "Pattern matching" for message handling seems extremely poweful - HOW IMPLEMENT? EXAMPLE?
- Can migrate from bad code in "app" and if proved useful migrate to core services. (Build it quickly, make a mess)
- Have a long tail of services hLoc (some massive horroble ones, lots of small ones)
- New features are new services. Deliberately have low-quality services. Choose the services that count. 
- Testing done by sending messages to in / out (not mocking / unit tests). Uniform. Can live test the system. 
- UX is really really hard. Double diamond diagram - standard approach to UX. Use a process for the front end. Architecture is more important 
- Express the system as messages. Build a command line app before a UI!
- People use Kubernetes to run microservices independently. Important to be able to bundle and deploy together in same process.
- Paul Graham beating the average (lisp) - always have a message REPL
- They don't have a UI yet for all the users/ groups/ etc. - can do it all thru the repl.
- http://senecajs.org/ 
- Make sure the entire system can run in one process locally
- They use a "service mesh" gossip protocol
- They use one MongoDB (haven't needed to separate DB per service)
- Microservices need to be components

Three Years of Lessons from Running Potentially Malicious Code Inside Container.
Ben Hall (Katacoda - check this out)
--------------------------------------------------------------------------------
- Docker security 101 overview
- cgroups - give containers resource limits
- kill things with a timeout (things should be idempotent)
- coin mining and 3d rendering
- Docker has got better at this now (eg can set a flag to stop infinite processes)
- Quick wins:
  - don't allow root
  - read only filesystems
  - block egress

18 Heuristics to Discover your Contexts Boundaries.
Cyrille Martraire
---------------------------------------------------
**This was really really useful, real life examples of DDD**
*Author has a book coming out*

- Microservices need DDD to save them from disaster
- How to partition your system / how do we define boundaries 
- Easy way
  - by layer
  - by technology
  - by entity (product / user / whatever)
- better way
  - DDD by Eric Evans of course:
  - functional area (bounded context)
 - Eg
   - catalog
   - recommendation
   - billing
   - shopping cart
how will things change (if will change independently)
- names
- independence implies some duplication
- BCs : we decide to reduce coupling at the expense of redundancy
- different models of the same thing (probably sharing an ID) in each BC
- shipping/shippable vs catalogue/book
- subdomain names usually end in 'ing' or 'tion' - they have a purpose (verbs made into nouns)
- potato diagrams
- event storming (group business events together)

Event Driven Collaboration.
Ian Cooper
--------------------------
- Microservices - at least two conceptions: Tiny (cell-like) vs ABC (larger)

Lightning Talk: How to Explain Microservices to your Grandma.
Francesco Renzi
-------------------------------------------------------------
Ok...

A Hitchhikers Guide to Improving Observability in a Hybrid Universe.
Alex Close (Elastic)
--------------------------------------------------------------------
- Ebay stores 1 petabyte daily in Elastic
- Space satellite applications
- Elastic stack
- Uptime monitoring in Kibana - Kibana being developed

Day 2
=====

Keynote: Getting to DDD: Pragmatic or Principled?
Julie Lerman
-------------------------------------------------
- DDD purists / terminology could be shutting people out from learning DDD
- Passing knowledge on to your team - how? It's too much. 
- 

Takeaways
---------
- Docker is still massive (obviously)
- React is still massive
- Kubernetes is massive. Red Hat OpenShift is a commercial offering based on Kubernetes for enterprises.
- The infra / ops side of things is massive, overwhelming, skills shortage 
- In many ways the industry is still trying to get to DDD
- Microservices are rebranded SOA, which is rebranded webservices. People are still making the same mistakes
- Big emoji poo --> lots of small emoji poos
