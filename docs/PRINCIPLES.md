# Adaptive Presence — Foundational Principles

## 1. First-Principles Architecture

Adaptive Presence must begin from fundamental requirements rather than existing infrastructure products.

The architecture must not assume that:

- servers are fundamental
- cloud infrastructure is fundamental
- datacenters are fundamental
- containers are fundamental
- virtual machines are fundamental
- Kubernetes is fundamental
- peer-to-peer networking is always sufficient
- centralized infrastructure is always required
- serverless computing is the correct abstraction

Existing technologies may eventually be used as implementation mechanisms.

They must not define the conceptual model before the requirements are understood.

---

## 2. Computational Presence Is Not Permanently Located

A logical service must not be assumed to permanently reside on a particular machine.

Its computational presence may:

```text
appear
expand
contract
move
split
merge
replicate
stop
restart
recover








# Adaptive Presence — Foundational Principles

## 1. First-Principles Architecture

Adaptive Presence must begin from fundamental requirements rather than existing infrastructure products.

The architecture must not assume that:

- servers are fundamental
- cloud infrastructure is fundamental
- datacenters are fundamental
- containers are fundamental
- virtual machines are fundamental
- Kubernetes is fundamental
- peer-to-peer networking is always sufficient
- centralized infrastructure is always required
- serverless computing is the correct abstraction

Existing technologies may eventually be used as implementation mechanisms.

They must not define the conceptual model before the requirements are understood.

---

## 2. Computational Presence Is Not Permanently Located

A logical service must not be assumed to permanently reside on a particular machine.

Its computational presence may:

```text
appear
expand
contract
move
split
merge
replicate
stop
restart
recover

The logical identity of the service should remain distinct from its current physical execution.

3. Capability Over Hardware Category

The architecture must reason primarily about capabilities rather than hardware labels.

The system should not fundamentally care whether a capability comes from:

phone
tablet
laptop
desktop
server
datacenter
cloud resource
embedded device
future computing device

Instead it should reason about properties such as:

compute
memory
storage
network
connectivity
energy
availability
latency
trust
security
specialized hardware

Hardware categories are implementation details unless a requirement makes them relevant.

4. Capability Availability Is Independent

A device is not simply "available" or "unavailable."

Different capabilities may have different availability states.

For example:

compute       available
storage       unavailable
network       available
battery       limited
trusted exec  unavailable

Scheduling and adaptation should therefore operate at the capability level whenever practical.

5. Demand Drives Presence

Computational presence should be created or modified because there is a reason for it to exist.

Possible reasons include:

user activity
service requirements
data availability
recovery requirements
communication requirements
performance requirements
security requirements

The system should investigate whether unnecessary computation can disappear when the corresponding demand disappears.

6. User Activity Is Part of Demand

Demand is not equivalent to CPU utilization.

The system should consider:

who is active
what they are doing
what services they require
what capabilities those services require

The architecture should therefore investigate a relationship between:

users
    ↓
intent
    ↓
required capabilities
    ↓
services
    ↓
computational presence
7. Logical State Is Independent of Execution Location

Logical state must not be permanently bound to the machine currently executing a responsibility.

If execution changes:

Node A
   ↓
Node B

the logical state and authority associated with the service should remain conceptually continuous.

This principle is essential for migration and recovery.

8. Ownership Is Independent of Execution

A device providing computation does not automatically become the owner of the data or service it executes.

The architecture must distinguish:

ownership
authority
execution
storage
custody

These may exist in different locations or under different actors.

9. Trust Must Be Explicit

A capability provider must not automatically be trusted simply because it participates in computation.

Trust must be established and evaluated explicitly.

The architecture should investigate:

identity
authentication
authorization
capabilities
cryptographic verification
encryption
integrity
attestation where applicable
reputation where applicable

Trust may also change over time.

10. Failure Is a Normal Lifecycle State

The architecture must assume that participants can disappear.

Normal lifecycle events include:

join
participate
leave
disappear
return
move
degrade
recover

Failure handling must therefore be intrinsic to the system rather than added after the primary architecture is designed.

11. Adaptation Is Continuous

Adaptive Presence should not be designed around one-time deployment decisions.

The environment changes continuously.

Therefore the system should potentially reevaluate:

demand
capabilities
connectivity
trust
availability
performance
energy
security

and adjust computational presence accordingly.

12. Minimum Necessary Presence

The system should investigate whether it can satisfy requirements using the minimum necessary active computational presence.

Conceptually:

Required capability
        +
Constraints
        ↓
Minimum suitable presence

This does not mean minimizing resources at all costs.

Security, reliability, performance, privacy, recovery, and other requirements may justify additional resources.

The objective is:

Avoid unnecessary infrastructure while satisfying the actual requirements.

13. Composition Is Preferable to Assumption

A service should not automatically be assumed to require one machine.

The architecture should allow investigation of compositions such as:

compute → Node A
storage → Node B
network → Node C
recovery → Node D

A logical service may therefore be a composition of capabilities.

Whether this is practical must be experimentally determined.

14. Communication Is Opportunistic

The architecture must not assume that Internet connectivity is always available.

Potential communication mechanisms include:

Internet
local network
Wi-Fi
Wi-Fi Direct
Bluetooth
USB
cellular
nearby devices
future communication mechanisms

The system should operate at the highest communication capability currently available without assuming that every environment provides the same connectivity.

15. Local Operation Is Fundamental

The architecture should investigate whether meaningful operation is possible without remote infrastructure.

A first device should potentially be capable of establishing an initial local presence.

Remote infrastructure should be an enhancement rather than an absolute prerequisite wherever physically and technically possible.

16. Physical Limitations Must Be Honored

Adaptive Presence must never claim to eliminate physical limitations.

If a capability fundamentally requires:

persistent connectivity
global routing
stable storage
global coordination
trusted hardware
legal authority

then that requirement must be explicitly modeled.

The architecture must distinguish:

not yet solved

from:

physically impossible under the assumed conditions
17. Centralization and Decentralization Are Tools

The architecture must not treat either centralization or decentralization as an ideology.

A requirement may be best served by:

one node
multiple nodes
local coordination
federation
community infrastructure
dedicated infrastructure
cloud infrastructure

The architecture should determine the appropriate structure from requirements and constraints.

18. Infrastructure Providers Are Interchangeable Sources of Capability

If conventional infrastructure becomes available, Adaptive Presence should be able to investigate using it without changing the logical application model.

A cloud resource and a personal computer may expose different capabilities, but both can potentially participate as capability providers.

The infrastructure source should therefore remain below the application abstraction boundary.

19. Application and Infrastructure Must Be Separated

Applications should express:

intent
requirements
required capabilities
security requirements
availability requirements

They should not need to express:

server addresses
machine identities
datacenter regions
database hosts
container placement
cloud provider topology

Adaptive Presence should investigate whether these implementation decisions can remain inside the infrastructure layer.

20. Generality

Adaptive Presence should not be designed around one application category.

The architecture should seek primitives that could potentially support:

organizations
messaging
search
media
AI
collaboration
storage
scientific workloads
IoT
gaming
future applications

Domain-specific behavior should remain above the foundational presence layer whenever practical.

21. Security Is a First-Class Constraint

Security must participate in placement and adaptation decisions.

A computational location that is faster or cheaper may still be unacceptable if it violates:

privacy
confidentiality
integrity
authority
trust
compliance

Therefore security is not merely a perimeter around the architecture.

It is part of the adaptation problem itself.

22. Recovery Is Part of Normal Operation

Recovery must not be treated as a separate emergency subsystem.

Because disappearance is normal, the architecture should continuously consider:

where state exists
how state can be reconstructed
which capabilities can assume responsibility
how authority is preserved
how conflicting state is reconciled
23. No Permanent Global Presence Is Assumed

Adaptive Presence must investigate whether useful global systems can operate without requiring one permanently active global execution location.

This does not imply that persistent infrastructure is impossible or unnecessary.

It means that persistent infrastructure must be justified by an actual requirement.

24. Every Assumption Is Challengeable

No proposed abstraction is sacred.

This includes:

node
service
presence
capability
state
identity
trust
execution

If experiments demonstrate that an abstraction is unnecessary, insufficient, or misleading, it should be replaced.

25. Hypotheses Must Be Falsifiable

The project must distinguish clearly between:

fact
assumption
hypothesis
design choice
experiment
result

An attractive architectural idea must not become an architectural rule merely because it sounds plausible.

26. Experiments Before Large Implementation

The project should prefer small experiments that answer precise questions.

The development loop is:

hypothesis
    ↓
model
    ↓
experiment
    ↓
measurement
    ↓
failure analysis
    ↓
revision
    ↓
implementation

Large implementation should follow validated architectural understanding rather than replace it.

27. Existing Technologies Are Implementation Options

Technologies such as:

operating systems
databases
containers
virtual machines
cloud platforms
distributed databases
network protocols
cryptographic systems

may eventually be useful.

However, selecting a technology must follow a demonstrated requirement.

The project must never begin with:

Which existing technology should become the architecture?

It should begin with:

What capability does the architecture require?

28. Terminal and Development Environment Independence

The project must avoid unnecessary assumptions about:

operating system
shell
absolute paths
installed software
services
hardware
development environment

The implementation environment may change between development sessions.

Project instructions should therefore verify the actual environment when necessary and prefer portable procedures.

29. Terminal and Chat Representation Are Not Authoritative

Terminal output and ChatGPT transcript rendering may visually alter:

paths
filenames
symbols
spacing
special characters
commands
formatting

Visual representation in the conversation must not be treated as proof of filesystem corruption.

When exact paths, filenames, or symbols matter, the project should use robust verification such as:

literal output
byte-oriented inspection
filesystem queries
Git state

The actual filesystem and command results are authoritative.

30. The Architecture Must Be Able to Say "No"

If a proposed capability cannot be provided under current constraints, the system must be able to represent that honestly.

For example:

required capability:
    global reachability

available capabilities:
    local network only

result:
    global reachability unavailable

The architecture should not hide impossible requirements behind unreliable abstractions.

31. Fundamental Principle

The highest-level principle of Adaptive Presence is:

Do not begin with a place where computation lives. Begin with a requirement for computation and determine what computational presence can naturally emerge from the capabilities currently available.

This principle governs the research direction of the entire project.
