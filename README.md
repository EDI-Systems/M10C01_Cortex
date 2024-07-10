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

## EDI Project Information
- M10C01 R1T1

## Starring Contributors
