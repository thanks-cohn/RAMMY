```
================================================================================
██████╗  █████╗ ███╗   ███╗███╗   ███╗██╗   ██╗
██╔══██╗██╔══██╗████╗ ████║████╗ ████║╚██╗ ██╔╝
██████╔╝███████║██╔████╔██║██╔████╔██║ ╚████╔╝
██╔══██╗██╔══██║██║╚██╔╝██║██║╚██╔╝██║  ╚██╔╝
██║  ██║██║  ██║██║ ╚═╝ ██║██║ ╚═╝ ██║   ██║
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚═╝     ╚═╝   ╚═╝

A FABRIC-NATIVE DISTRIBUTED MEMORY KERNEL
================================================================================
```

A FABRIC-NATIVE DISTRIBUTED MEMORY KERNEL


Machines die.
Memory remains.
The fabric remembers.


GRAND VISION

RAMMY is an experimental distributed operating system and kernel architecture
designed around one central idea:

    THE NETWORK IS THE COMPUTER.

We reject the traditional model:

    one motherboard
    one RAM pool
    one operating system instance
    one machine identity

Instead:

    RAM belongs to the fabric
    processes belong to the fabric
    computation belongs to the fabric
    machines become organs inside one computational organism

RAMMY seeks to create a true distributed memory civilization:
a unified computer composed of many physical nodes.


WHAT WE INTEND TO BUILD


[1] POOLED FABRIC RAM

All node memory contributes to one global memory civilization.

Memory becomes:
    near memory
    far memory
    replicated memory
    migrating memory
    leased memory
    persistent memory

not:
    "RAM physically trapped inside one machine."

Pages can:
    migrate
    replicate
    relocate
    survive node death
    follow computation

The kernel understands memory topology and distance.


[2] GLOBAL PROCESS IDENTITY

Processes are NOT tied to machines.

Processes may:
    pause
    migrate
    resume
    replicate
    fail over

without losing identity.

A process should survive hardware death whenever possible.


[3] DISTRIBUTED NUMA FABRIC

RAMMY treats the cluster as one giant NUMA organism.

The scheduler understands:
    topology
    latency
    congestion
    thermal state
    bandwidth
    memory locality
    failure probability

The scheduler moves:
    memory toward computation
or:
    computation toward memory

depending on cost.


[4] FABRIC-NATIVE PAGE MANAGEMENT

The global memory manager (GMEM) tracks:

    page owner
    replicas
    dirty state
    temperature
    migration cost
    coherence state
    fault state

Memory modes include:

    LOCAL_PRIVATE
    REMOTE_READ
    REMOTE_OWNED
    REPLICATED_IMMUTABLE
    SHARED_LEASE
    MESSAGE_OWNED

We explicitly avoid magical incoherent memory chaos.


[5] FAILURE-TRANSPARENT COMPUTING

Machines are expected to fail.

RAMMY treats node death as a normal condition.

The system continuously:
    monitors nodes
    predicts failure
    migrates workloads
    replicates hot pages
    evacuates state

The goal:

    COMPUTATION CONTINUES.


[6] TRANSPARENT SYSTEM DESIGN

No hidden magic.
No invisible orchestration theater.

Every:
    migration
    page move
    scheduler decision
    ownership transfer
    failure event
    replication action

is logged and inspectable.

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
    cross-compilation
    fast builds
    inspectable binaries
    modern systems ergonomics without abstraction rot

SECONDARY LANGUAGE:
    C

USED FOR:
    bootstrap code
    architecture glue
    hardware bring-up
    legacy low-level interfaces

NO C++ IN THE KERNEL CORE.

Possible future Rust usage:
    isolated drivers
    sandboxed parsers
    untrusted modules

Rust is NOT the founding systems language.


CORE SUBSYSTEMS

fabric/
    node discovery
    topology map
    heartbeat
    latency tracking
    bandwidth awareness

gmem/
    global memory manager
    page ownership
    replication
    migration
    coherence

sched/
    topology-aware scheduler
    memory-aware execution
    thermal balancing
    migration policy

proc/
    global process identity
    checkpointing
    migration
    failover

cap/
    capability-based authority system

fault/
    node failure detection
    evacuation logic
    recovery systems

log/
    battle-report logging
    migration traces
    page history
    system truth layer


INITIAL DEVELOPMENT STRATEGY

PHASE 1:
    Linux-hosted simulation environment

Multiple RAMMY nodes run as Linux processes.

We simulate:
    pooled pages
    remote memory
    migration
    replication
    node failure

before bare metal.

PHASE 2:
    distributed page mapping

Machine A allocates pages.
Machine B maps them remotely.

PHASE 3:
    process migration

Move execution toward hot memory regions.

PHASE 4:
    fault-transparent execution

Kill nodes.
Processes survive.

PHASE 5:
    bare-metal distributed kernel

The fabric becomes the machine.


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

A node is not a computer.

A node is an organ.

The fabric is the machine.

Machines are temporary.
Processes migrate.
Memory persists.

THE FABRIC REMEMBERS.
```

```
```text id="3r8h0v"

FUTURE FABRIC VISION

RAMMY is designed around a future where networking and memory fabrics
become fast enough that remote memory behaves less like storage and more
like distant NUMA memory.

As bandwidth and latency improve through technologies such as:

    100GbE+
    400GbE+
    800GbE+
    RDMA
    Optical interconnects
    CXL memory fabrics

the distinction between:
    "local machine"
and:
    "remote machine"

begins to weaken.

Under this model, multiple ordinary computers can contribute:

    RAM
    CPU
    storage
    accelerators
    bandwidth

into one unified computational fabric.

RAMMY dynamically manages:

    page placement
    replication
    process migration
    topology-aware scheduling
    memory locality
    failure recovery

The system continuously decides whether it is cheaper to:

    move memory toward computation
or:
    move computation toward memory

The long-term objective is not clustered computers.

The objective is:

    ONE DISTRIBUTED MACHINE

A node is an organ.
The fabric is the computer.

```

```text id="8v4x2n"

GENERATIVE AI AND FABRIC MEMORY

RAMMY is especially suited for future large-scale generative workloads:

    Large Language Models (LLMs)
    Stable Diffusion
    Video generation systems
    Multimodal reasoning systems
    Simulation engines
    Persistent AI memory systems

These workloads are increasingly constrained not only by compute,
but by memory capacity and memory movement.

Modern systems often require:
    massive VRAM pools
    high system RAM
    tensor sharding
    model partitioning
    checkpoint offloading

RAMMY approaches this differently.

Instead of requiring one enormous machine, RAMMY allows multiple
ordinary nodes to contribute resources into one distributed fabric.

Example:

    5 machines with:
        64GB RAM each

can become:

    ~320GB pooled memory fabric

allowing models larger than any individual node could normally host.

Even under CPU constraints, this remains valuable because:

    model weights can remain resident in pooled memory
    KV caches can be distributed
    tensor regions can migrate dynamically
    inactive layers can remain remote
    workloads can be partitioned across nodes
    inference can continue without extreme local VRAM requirements

RAMMY does not assume infinite speed or magical physics.

The kernel understands:
    locality
    bandwidth
    migration cost
    memory heat
    topology distance

The scheduler continuously optimizes execution placement to reduce
unnecessary memory movement across the fabric.

The long-term goal is to make large-scale generative systems possible
on distributed collections of ordinary machines rather than requiring
single monolithic hardware systems.

```

AI TRAINING AND DISTRIBUTED SUPERCOMPUTING

RAMMY is designed with the belief that future computational power
should not belong exclusively to corporations with massive datacenters.

The long-term vision is a world where ordinary people can assemble
distributed supercomputers from collections of normal machines.

Under RAMMY:

    old desktops
    spare laptops
    home servers
    workstation clusters
    garage compute nodes

can contribute resources into one computational fabric.

Five ordinary machines may become:

    one large memory organism
    one distributed AI runtime
    one pooled training system

This is especially important for:

    LLM training
    Stable Diffusion training
    video generation
    multimodal AI
    scientific simulation
    reinforcement learning
    agent systems
    persistent memory AI

Modern AI increasingly depends on:

    massive RAM pools
    large VRAM pools
    tensor sharding
    distributed inference
    distributed training
    checkpoint management
    memory locality optimization

RAMMY aims to make these workloads possible across distributed
collections of ordinary hardware.

Even under CPU constraints, distributed memory remains extremely valuable.

Large models are often bottlenecked by:

    memory capacity
    tensor storage
    KV cache growth
    checkpoint size
    dataset residency
    parameter movement

rather than raw compute alone.

Under RAMMY:

    model weights can remain distributed
    training shards can migrate dynamically
    memory-heavy layers can remain resident remotely
    tensor regions can replicate across nodes
    inactive regions can move to colder fabric memory
    training jobs can scale across pooled systems

The kernel continuously optimizes:

    topology
    memory locality
    migration cost
    bandwidth pressure
    execution placement

The goal is not merely distributed computing.

The goal is democratized supercomputing.

A future where anyone with enough connected machines can participate in:

    advanced AI
    large-scale simulation
    distributed research
    generative systems
    computational science

without requiring ownership of a monolithic enterprise machine.

RAMMY envisions a future where:

    SUPERCOMPUTERS ARE GROWN,
    NOT PURCHASED.





