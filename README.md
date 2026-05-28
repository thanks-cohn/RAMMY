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

Machines die.
Memory remains.
The fabric remembers.

================================================================================
GRAND VISION
================================================================================

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

================================================================================
WHAT WE INTEND TO BUILD
================================================================================

[1] POOLED FABRIC RAM
----------------------------------------

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

================================================================================
[2] GLOBAL PROCESS IDENTITY
----------------------------------------

Processes are NOT tied to machines.

Processes may:
    pause
    migrate
    resume
    replicate
    fail over

without losing identity.

A process should survive hardware death whenever possible.

================================================================================
[3] DISTRIBUTED NUMA FABRIC
----------------------------------------

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

================================================================================
[4] FABRIC-NATIVE PAGE MANAGEMENT
----------------------------------------

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

================================================================================
[5] FAILURE-TRANSPARENT COMPUTING
----------------------------------------

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

================================================================================
[6] TRANSPARENT SYSTEM DESIGN
----------------------------------------

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

================================================================================
LANGUAGES
================================================================================

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

================================================================================
CORE SUBSYSTEMS
================================================================================

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

================================================================================
INITIAL DEVELOPMENT STRATEGY
================================================================================

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

----------------------------------------

PHASE 2:
    distributed page mapping

Machine A allocates pages.
Machine B maps them remotely.

----------------------------------------

PHASE 3:
    process migration

Move execution toward hot memory regions.

----------------------------------------

PHASE 4:
    fault-transparent execution

Kill nodes.
Processes survive.

----------------------------------------

PHASE 5:
    bare-metal distributed kernel

The fabric becomes the machine.

================================================================================
INFLUENCES
================================================================================

Amoeba
Sprite
Plan 9
Kerrighed
MOSIX
Distributed NUMA research
Capability systems
RDMA fabrics
Future CXL architectures

================================================================================
FINAL DOCTRINE
================================================================================

A node is not a computer.

A node is an organ.

The fabric is the machine.

Machines are temporary.
Processes migrate.
Memory persists.

THE FABRIC REMEMBERS.
================================================================================
