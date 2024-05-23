# GNC generic networked computing kernel

&ensp;&ensp;**GNC** is a metakernel for orchestrating networked computing resources in a manner that is transparent to the user. It expands the traditional operating system concepts such as task scheduling, memory management, file system and synchronization over the entire local- or wide- area networks, and abstracts the underlying details of the computing infrastructure away.

## Quick Demo


## The Need for Unification and Abstraction


## System Design

The current design, v1, only involves deploying WASM sandboxes on platforms that may support them. The communication protocol is still undetermined. In general, this framework should complete discovery, enumeration, and capability attestation. Given their runtime capabilities, the application is thus disseminated into packs that are then carried out on the framework.

Device enumeration -> Resource attestation -> Runtime pool
                                                             -> Tasklet/Runtime matching -> Dynamic scheduling
Task/SLA description -> Tasklet/SLO DAG -> Tasklet/SLO pool 
------------------------------------------------------------------------------------------------------------------
Fault-tolerance&Security     Incentive matching      Programming environment     Development toolchain      Others


###What kind of runtime could the device provide?
- Generic - WASM then transcompile. Best security so far, and best compatibility.
- Native - W/native instruction set and ABI, usually an environment, i.e. OS type, libraries installed, etc.
- Specific - A specific computing resource with unusual characteristics i.e. GPU, compiler, etc.

###How to deal with potential security issues, particularly confidentiality?
- Homomorphic computing - full homo is too expensive
- Homomorphic swapping - might be a choice when we run out of ram, just encrypt before you swap
- Homomorphic storage is easy as we just need to apply encryption
- Secure multi-party computation - expensive as hell, and (very) restrictive
- Just trust - if we know the node well
- Doesn't seem to be more choices

###Fault-tolerance
- RAFT to tolerate off-line nodes
- PBFT even stronger to tolerate sabotage w/more resources
- Blockchain could really kick in here to build a shared data space

###What demo applications then?
Tasks that are unamenable w/single node. This usually means
- Data not local - cloud computing would fail here
- Display not local - or even no display - if there is, someone needs to provide RDP runtime
- Node resource insufficient - need resource consolidation

###Permission management
- Capability-based management w/network-level attestation algorithms
- ZKP tech


## Holistic Archives and Records of Similar Ideas
<div align="center">

__The heritage of the past is the seed that brings forth the harvest of the future. -- Wendell Phillips__

</div>

&ensp;&ensp;The concept of system resource consolidation is always pronounced among researchers and there has been a rich publication of similar ideas, albeit with mixed success. To honor their contributions, avoid their pitfalls and borrow their gists, we need to scrutinize them with due caution.

### Early research on mainframes

### Early research on supercomputers

### Early research on memory models

### Grid computing

### Cloud computing
"GNC's not cloud"

### Edge/fog computing

### Pervasive computing

### Computing power network

### Blockchain/BFT protocols

### NCCL etc. libraries



## Commercial and engineering efforts
<div align="center">

__The engineer has been, and is, a maker of history. -- James Kip Finch__

</div>

### Sunlogin/Teamviewer remote desktops

### RDP remote desktop protocol

### Sunshine/moonlight game streaming

### Cloud gaming technologies

### Netcafe diskless environments

### ScaleMP vSMP consolidation solutions

### MapReduce framework

### Nginx etc. reverse proxy

### BOINC/SETI@Home/Folding@Home

### RDMA/RoCE/Infiniband

### CXL/PCIe technologies

### Transcendental memory/Memory balloons

## Standing on the Shoulders of the Giants
<div align="center">

__What's past is prologue -- William Shakespeare__

</div>

## EDI Project Information
- M10C01 R1T1

## Starring Contributors
