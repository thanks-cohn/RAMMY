```text
██████╗  █████╗ ███╗   ███╗███╗   ███╗██╗   ██╗
██╔══██╗██╔══██╗████╗ ████║████╗ ████║╚██╗ ██╔╝
██████╔╝███████║██╔████╔██║██╔████╔██║ ╚████╔╝
██╔══██╗██╔══██║██║╚██╔╝██║██║╚██╔╝██║  ╚██╔╝
██║  ██║██║  ██║██║ ╚═╝ ██║██║ ╚═╝ ██║   ██║
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚═╝     ╚═╝   ╚═╝

A FABRIC-NATIVE DISTRIBUTED MEMORY KERNEL


Machines die.
Memory remains.
The fabric remembers.


GRAND VISION

RAMMY is an experimental distributed operating system and memory kernel
designed around one central idea:

    THE NETWORK IS THE COMPUTER.

Modern computing still treats machines as isolated islands:

    one motherboard
    one RAM pool
    one operating system instance
    one machine identity

RAMMY rejects this model.

Instead:

    RAM belongs to the fabric
    processes belong to the fabric
    computation belongs to the fabric

A node is not a computer.

A node is an organ inside one distributed computational organism.


WHAT RAMMY INTENDS TO BUILD


[1] FABRIC MEMORY

All nodes contribute resources into one unified memory fabric.

Memory becomes:

    near memory
    far memory
    replicated memory
    migrating memory
    persistent memory

Pages may:

    migrate
    replicate
    relocate
    survive node failure
    follow execution dynamically

RAMMY treats remote memory not as storage,
but as distant NUMA memory.


[2] DISTRIBUTED PROCESS IDENTITY

Processes are not permanently tied to hardware.

Processes may:

    pause
    migrate
    resume
    fail over
    relocate near hot memory regions

without losing identity.

The objective is continuity beyond machine death.


[3] TOPOLOGY-AWARE SCHEDULING

The scheduler continuously evaluates:

    memory locality
    bandwidth
    latency
    congestion
    thermal state
    migration cost
    node health

The kernel dynamically decides whether it is cheaper to:

    move memory toward computation
or:
    move computation toward memory


[4] FABRIC-NATIVE PAGE MANAGEMENT

The global memory manager (GMEM) tracks:

    ownership
    replicas
    dirty state
    migration priority
    memory temperature
    coherence state
    failure state

Memory modes include:

    LOCAL_PRIVATE
    REMOTE_READ
    REMOTE_OWNED
    REPLICATED_IMMUTABLE
    SHARED_LEASE
    MESSAGE_OWNED

RAMMY intentionally avoids pretending physics does not exist.

Distance matters.
Topology matters.
Latency matters.

The kernel is designed to understand this reality,
not hide it.


[5] FAILURE-TRANSPARENT COMPUTING

Machines are expected to fail.

The system continuously:

    monitors nodes
    predicts instability
    migrates workloads
    replicates hot pages
    evacuates critical state

The objective is simple:

    COMPUTATION CONTINUES.


[6] TRANSPARENT SYSTEM DESIGN

No hidden orchestration theater.
No invisible abstractions.

Every:

    migration
    page transfer
    scheduler action
    ownership change
    replication event
    failure response

is inspectable and logged.

Logs are battle reports.


LANGUAGES

PRIMARY LANGUAGE:
    ZIG

WHY ZIG:

    transparent control flow
    no hidden runtime
    explicit allocation
    low-level systems access
    strong C interoperability
    fast iteration
    inspectable binaries
    modern systems ergonomics without abstraction rot

SECONDARY LANGUAGE:
    C

USED FOR:

    bootstrap code
    architecture glue
    hardware bring-up
    low-level compatibility layers

NO C++ IN THE KERNEL CORE.


CORE SUBSYSTEMS

fabric/
    node discovery
    topology maps
    heartbeat
    latency tracking
    bandwidth awareness

gmem/
    global memory manager
    page ownership
    migration
    replication
    coherence

sched/
    topology-aware scheduler
    locality optimization
    execution placement

proc/
    distributed process identity
    migration
    checkpointing
    failover

cap/
    capability-based authority system

fault/
    failure detection
    evacuation logic
    recovery systems

log/
    battle-report logging
    migration history
    system truth layer


INITIAL DEVELOPMENT STRATEGY

PHASE 1:
    Linux-hosted simulation environment

Multiple RAMMY nodes run as Linux processes.

Simulate:

    pooled pages
    remote memory
    migration
    replication
    node failure

before bare metal deployment.


PHASE 2:
    Distributed page mapping

Machine A allocates pages.
Machine B maps them remotely.


PHASE 3:
    Process migration

Move execution dynamically toward hot memory regions.


PHASE 4:
    Failure-transparent execution

Kill nodes.
Processes survive.


PHASE 5:
    Bare-metal distributed kernel

The fabric becomes the machine.


AI, TRAINING, AND DISTRIBUTED SUPERCOMPUTING

RAMMY is designed for a future where advanced computation is no longer
restricted to massive enterprise systems.

Under RAMMY:

    old desktops
    spare workstations
    home servers
    garage compute clusters

can contribute resources into one computational fabric.

Five ordinary machines may become:

    one large memory organism
    one distributed AI runtime
    one pooled training system

This is especially important for:

    Large Language Models
    Stable Diffusion
    video generation
    multimodal systems
    scientific simulation
    reinforcement learning
    persistent AI systems

Modern AI workloads are increasingly constrained by:

    memory capacity
    VRAM limits
    tensor movement
    checkpoint size
    KV cache growth
    model residency

rather than raw compute alone.

RAMMY allows:

    distributed model residency
    pooled memory fabrics
    distributed training
    distributed inference
    remote tensor residency
    dynamic execution placement

without requiring one monolithic machine.

As networking technologies evolve through:

    RDMA
    optical interconnects
    CXL memory fabrics
    ultra-high-bandwidth Ethernet

remote memory increasingly behaves less like storage and more like
distant NUMA memory.

The long-term vision is a world where ordinary people can assemble
distributed supercomputers from collections of normal hardware.

Not clustered computers.

One distributed machine.


INFLUENCES

    Amoeba
    Sprite
    Plan 9
    Kerrighed
    MOSIX
    Distributed NUMA research
    Capability systems
    RDMA fabrics
    Future CXL architectures


FINAL DOCTRINE

A node is an organ.

The fabric is the machine.

Machines are temporary.
Processes migrate.
Memory persists.

THE FABRIC REMEMBERS.
```
