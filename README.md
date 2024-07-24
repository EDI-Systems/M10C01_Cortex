# GNC generic networked computing kernel

&ensp;&ensp;**GNC** is a metakernel for orchestrating networked computing resources in a manner that is transparent to the user. It expands the traditional operating system concepts such as task scheduling, memory management, file system and synchronization over the entire local- or wide- area networks, and abstracts the underlying details of the computing infrastructure away.

## TODO
### Fill in the readme
For each subtopic, a 1000-word paragraph must be written to describe (1) what is the stuff, (2) who did it under for what scenario, (3) common advantages and shortcomings of the system, and (4) what fundamental design decision made the system exhibit its characteristics, and particularly (5) why its approach does not fit our case.

### Fill in the Document/Reference
Each reference part needs to be expanded to a paper. If you have less than 1000 references for each part when you finish it, you're probably off by pretty far. When doing the survey, it needs to be written as if you were to build a new system; you need to mention (1) what the paper did, (2) what influence it had, (3) today who's using the technique or why is the technique abandoned, and (4) what kind of design decisions we should make when we build the system. Feel free to change the latex templates provided, and each part can supply your own styles/bib as needed. We clean up later on.

## Quick Demo


## The Need for Unification and Abstraction

## Holistic Archives and Records of Similar Ideas
<div align="center">

__The heritage of the past is the seed that brings forth the harvest of the future. -- Wendell Phillips__

</div>

&ensp;&ensp;The concept of system resource consolidation is always pronounced among researchers and there has been a rich publication of similar ideas, albeit with mixed success. To honor their contributions, avoid their pitfalls and borrow their gists, we need to scrutinize them with due caution. A short comment for each field is provided below, and the detailed comments are [here](Document/Reference).

### Historical Paradigms
- Mainframe research
- Supercomputer research
- Memory model research

### Modern Paradigms
- Grid computing
- Cloud computing
- Edge/fog computing
- Pervasive computing
- Computing power network
- Distributed System related research
  - Blockchain/BFT protocols

### Software engineering
- NCCL etc. libraries
- CORBA-TAO/DCOM/SOAP/ICERPC infrastructure
  - CORBA even have real-time and mission-critical extensions.
  - Why did CORBA fail (or is unpopular now)?
    - Possibly due to growth of computation/communication power ratio, which will grow further in the future, as the speed of light is a basic limitation.
    - Serializing and deserializing time is negligible now, and REST seems ok because latency is the limitation here, not bandwidth; speed of light again here.
  - We should possibly base our ground abstraction upon a full message-passing model, but the implementation should vary.
    - How should we pass the messages, in a pubsub model, or a sndrcv notification model?
    - Variables are better in a pubsub model and the OS underlying could always optimize for that. Pubsub exposes causality in a better way as it provides a handle to group the receivers.
    - Notifications, blockings, are instead better to go through the sndrcv model. They are one-to-one in nature though you can make them pubsub as well.
    - Possibly have your APP/GROUPNAME or something else, and pubsub.
  - Other abstractions can __ALL__ drop upon message-passing, even shared memory. So we have forward compatibilities as well.
  - Language neutrality will be there, or not? It seems we need to have them, but some languages are just ill-suited to building such APPs.
- Blockchain/BFT protocols

## Commercial and engineering efforts
<div align="center">

__The engineer has been, and is, a maker of history. -- James Kip Finch__

</div>

### P2P protocols
- BT protocols
- Emule protocols

### Remote desktops
- Local-rendered
  - VNC
  - Sunlogin
  - Teamviewer
  - Sunshine/Moonlight
- Remote-rendered
  - RDP

### Hardware Sharing
- Generic virtualization
- Cloud gaming providers
- GPU virtualization
- Netcafe diskless environments
- Transcendental memory
- Memory balloons

### Hardware Consolidation
- ScaleMP vSMP consolidation solutions

### Distributed Frameworks
- Sun Grid Engine
- MapReduce framework
- Reverse Proxies
- BOINC/SETI@Home/Folding@Home
- Fluence network

### Physical Layer
- RDMA/RoCE
- CXL/PCIe
- Infiniband
- OmniPath (and how it died; see also ScaleMP vSMP solutions for fault tolerance)

## Standing on the Shoulders of the Giants
<div align="center">

__What's past is prologue -- William Shakespeare__

</div>

### a correct, low-level model that captures the essense of computation
- align with the laws of physics, 
  - theory of relativity; nothing is faster than light
  - quantum effects; there is ultimately a cap for everything, even if that cap is really high
- latency is impossible, but bandwidth is amenable 
  - the world fundamentally favors bandwidth.
- CAP is impossible, but ACID and BASE is plausible
  - the world fundamentally favors BASE.
  - but what about transactions? we like transactions, or we're to assume that transactions cannot exist (at least beyond some scale)?
- do not force a specific mental model or hardware organization, and thus will not age
  - the world is foundamentally slow or weak memory; "sequence" or "time", does not really exist in the universe.
- sufficiently versatile to take advantage of any given special mechanisms
  - the world is fundamentally diverse rather than unified; diversity is in its roots
  - support existing accelerators and inspire future ones
- PoW is fundamental, but BFT + Proof-of-sth-else (e.g. PoS) might be used as a retarded replacement
  - the world fundamentally favors proof-of-work, because hard work is blut und eisen, because macht geht vor recht
  - nice magic numbers: 1/3, 1/2, 2/3 - they end up in the constitution of many nations for a reason
  - we don't need global consensus, as such consensus does not fundamentally exist in the universe, for sure
- but we as humans are fond of an instant, ideal, unified, and ubiquitous computing experience

- looks like a multi-headed turing machine with slow publisher-subscriber memory, does that capture all the communication?
  - most attributes are on the memory - what consensus, fault-tolerance, and?
  - that should accept the same "language" theory wise so the capability is the same with the standard one.
  - but computing theory does not seem to help us here; it does not care about implementation properties i.e. efficiency.

### a multi-dimensional recursive organization
- for each task, a hierachy exists - not graphs but trees
  - are hierachies a fundamental construction of the universe?
  - i.e. are structures fundamental, or just a cognitive illusion?
- within each hierachy, the nodes are considered to be perfect
  - reliabilility, security and trust dimensions must be dealt with in each layer
  - the hierachies may be different in multiple dimensions - the hierachies on each layer may conflict with each other

### a meta programming language as an intermediate that captures the "intentions" of the computing task
- not a real programming language, but should serve as a compilation target where they could compile to
- describe intentions instead of styles, but what are "intentions"? are intentions objective, or subjective?
- would functional programming really kick in here? a functional intermediate language?

### a live JIT mechanism that maps the language to the actual implementation
- this is, so far, the easiest; previous researches exist largely in the wild.
- good artists copy great artists steal; we can just credit some existing some ideas.

### incentives. blockchain will kick in here just fine.

## EDI Project Information
- M10C01 R1T1

## Starring Contributors
