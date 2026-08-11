# Adaptive Presence — Candidate Primitives

## 1. Purpose

This document identifies candidate conceptual primitives for Adaptive Presence.

These are not final architectural components.

They are hypotheses about the smallest concepts that may be necessary to describe:

- computational demand
- available capabilities
- logical state
- execution
- communication
- trust
- adaptation
- continuity

Each primitive must remain open to revision, combination, replacement, or removal as research progresses.

---

## 2. Requirement

A Requirement represents something that must be satisfied.

Examples include:

```text
messaging
storage
computation
authentication
recovery
communication
low-latency execution
private execution

A requirement describes what must be achieved rather than where or how it should be achieved.

Conceptually:

Requirement
    |
    +-- capability requirements
    +-- security requirements
    +-- availability requirements
    +-- performance requirements
    +-- state requirements
3. Intent

Intent represents the purpose behind a requirement.

It may originate from:

user activity
application behavior
system operation
scheduled work
external events

Intent is potentially more semantic than raw resource demand.

For example:

User:
    "send a message"

Intent:
    messaging

Required capabilities:
    communication
    computation
    state

The project must determine how much semantic understanding the infrastructure actually needs.

4. Capability

A Capability represents something that a participant can provide.

Potential capability categories include:

compute
memory
storage
network
communication
specialized hardware
trusted execution
energy
availability
latency
geographic presence

A capability should not necessarily be considered binary.

For example:

compute:
    available
    capacity = limited

storage:
    available
    capacity = 500 GB

network:
    available
    bandwidth = variable

Capability may therefore have:

type
capacity
quality
availability
constraints
trust properties
5. Capability Provider

A Capability Provider is something that makes one or more capabilities available.

A provider could be:

phone
tablet
laptop
desktop
server
cloud resource
community resource
embedded device
future computing resource

The provider is not necessarily the same thing as a logical execution unit.

One provider may expose many capabilities.

A capability may potentially also be composed from multiple providers.

6. Participant

A Participant represents an entity that takes part in the Adaptive Presence environment.

A participant may be:

user
device
organization
service
application
capability provider
coordination participant

The project must determine whether these should actually share one abstraction or remain separate concepts.

7. Presence

Presence represents the currently available computational ability associated with a logical requirement or responsibility.

Presence is intentionally different from:

server
machine
process
container
virtual machine

A presence may exist across one or more physical resources.

Conceptually:

Logical responsibility
        |
        v
     Presence
      / | \
     /  |  \
 Node A Node B Node C

Presence may:

appear
expand
contract
move
split
merge
replicate
stop
recover

Whether "presence" is ultimately the correct abstraction is an open research question.

8. Execution Responsibility

Execution Responsibility represents the responsibility for performing some computation or operation.

This is deliberately separate from the physical location where execution occurs.

For example:

Logical responsibility:
    process incoming messages

Current execution:
    Node A

Later:

Logical responsibility:
    process incoming messages

Current execution:
    Node B

The responsibility remains logically continuous even though its physical execution changes.

9. State

State represents information required to preserve logical continuity.

Potential state includes:

identity
configuration
application data
service state
authorization state
history
metadata
recovery information

State must be investigated independently from execution.

The central question is:

How can logical state remain authoritative while execution responsibility changes?

10. Authority

Authority represents who or what has the right to control or modify logical state or perform an operation.

Authority must be distinguished from:

execution
storage
custody
physical possession

A device may temporarily execute a responsibility without becoming authoritative over it.

11. Identity

Identity represents the stable cryptographic or logical identity of an entity.

Potential identities include:

user
organization
service
device
capability provider

Identity should remain stable enough to support continuity even when physical execution changes.

The project must investigate:

identity creation
identity verification
identity recovery
identity delegation
identity revocation
12. Trust

Trust represents the degree to which a participant or capability can be relied upon for a particular operation.

Trust is not necessarily global.

For example:

Node A:
    trusted for public computation
    untrusted for private data

Node B:
    trusted for encrypted storage
    unavailable for real-time execution

Trust should therefore potentially be:

contextual
capability-specific
time-dependent
revocable
13. Constraint

A Constraint limits which computational arrangements are acceptable.

Potential constraints include:

privacy
security
latency
energy
bandwidth
availability
storage
geographic restrictions
legal requirements
hardware requirements
trust requirements

Constraints are important because the theoretically cheapest capability arrangement may not be acceptable.

14. Communication Path

A Communication Path represents a currently usable mechanism through which participants can exchange information.

Potential paths include:

Internet
local network
Wi-Fi
Wi-Fi Direct
Bluetooth
USB
cellular
nearby communication
future mechanisms

A communication path may have changing properties:

bandwidth
latency
reliability
cost
availability
range
security

Communication should therefore be treated as a capability rather than assumed to be permanently available.

15. Topology

Topology represents the currently observable relationships between participants and capabilities.

It may describe:

which participants can communicate
which capabilities are reachable
network characteristics
logical relationships
trust relationships
state relationships

Topology may change continuously.

Therefore the architecture must not assume a permanent physical topology.

16. Service

A Service represents a logical capability or behavior required by an application or participant.

Examples:

messaging
identity
storage
search
media processing
workflow
authentication

A Service is a logical concept.

Its execution location should remain separate.

For example:

Service:
    messaging

Current presence:
    Node A + Node B
17. Placement

Placement represents the current assignment of execution responsibility to available capabilities.

Conceptually:

Requirement
    ↓
Candidate capabilities
    ↓
Constraints
    ↓
Placement decision

Placement is not necessarily permanent.

It may change as:

demand changes
capabilities change
trust changes
network changes
nodes disappear
nodes appear
18. Adaptation

Adaptation represents the process by which the system changes computational presence in response to changing conditions.

Potential adaptation actions include:

start
stop
move
replicate
reduce
expand
reconfigure
recover

Adaptation is potentially continuous rather than a one-time deployment operation.

19. Migration

Migration represents the transfer of execution responsibility from one capability arrangement to another.

Example:

Responsibility
      |
      v
    Node A
      |
      | migration
      v
    Node B

Migration must preserve whatever properties are required for logical continuity.

The project must determine whether migration requires:

state transfer
state replication
responsibility transfer
checkpointing
reconstruction

or some combination of these.

20. Replication

Replication represents maintaining multiple computational or state representations for a purpose such as:

availability
recovery
performance
fault tolerance
geographic distribution

Replication should not automatically mean permanent duplication.

Adaptive Presence should investigate whether replicas can themselves be created and removed according to requirements.

21. Reconciliation

Reconciliation represents the process of resolving differences between independently evolving state or responsibilities.

This becomes important when:

nodes disconnect
nodes operate independently
nodes return
multiple replicas change

Potential mechanisms include:

versioning
causal relationships
conflict resolution
merge rules
authority rules
application-defined reconciliation

The correct mechanism is an open research question.

22. Recovery

Recovery represents restoration of required logical behavior after:

node disappearance
state loss
communication interruption
execution failure
capability degradation

Recovery should be based on whatever surviving capabilities and state remain available.

23. Availability

Availability represents whether a capability or responsibility can currently be used.

Availability may be:

fully available
partially available
intermittently available
degraded
temporarily unavailable

A capability may remain logically known even while currently unavailable.

24. Demand

Demand represents the currently required computational work or capability.

Demand may depend on:

active users
user intent
application activity
scheduled operations
external events
system recovery requirements

Demand should not be reduced to CPU utilization.

A system can have high semantic demand even when current CPU usage is low.

25. Resource

Resource represents a measurable physical or computational quantity.

Examples:

CPU
memory
storage
bandwidth
battery
energy
GPU capacity
network interfaces

Resources are lower-level than capabilities.

For example:

Resource:
    CPU capacity

Capability:
    execute computation

The architecture must determine how these concepts should relate.

26. Computational Group

A Computational Group represents multiple participants whose capabilities collectively provide a logical computational presence.

Example:

               Logical Service
                     |
        +------------+------------+
        |            |            |
     compute       storage     recovery
        |            |            |
      Node A       Node B       Node C

A Computational Group may be temporary.

It may change membership as capabilities appear or disappear.

Whether this primitive is actually necessary must be tested.

27. Logical Entity

A Logical Entity represents something that should remain conceptually continuous despite changes in physical execution.

Examples:

user
organization
service
application
logical dataset

A Logical Entity may have:

identity
authority
state
requirements
responsibilities

Its existence should not depend on one physical machine.

28. Presence Transition

A Presence Transition represents a change in the relationship between logical responsibilities and available capabilities.

Examples:

absent → present
present → expanded
present → reduced
present → moved
present → replicated
present → degraded
present → absent

Studying these transitions may be more fundamental than studying "deployment."

29. Decision

A Decision represents an adaptive choice about how requirements should currently be satisfied.

Possible decisions include:

where to execute
what to replicate
what to stop
what to start
which capabilities to combine
which node to trust
when to migrate

A decision should be evaluated against:

requirements
constraints
available capabilities
current topology
trust
cost
risk
30. Observation

An Observation represents information about the current environment.

Potential observations include:

node availability
capability capacity
network state
demand
user activity
trust changes
state divergence
energy conditions

Adaptation depends on observations.

The architecture must investigate how observations are collected without creating excessive overhead or centralized dependencies.

31. Event

An Event represents something that may cause or require adaptation.

Examples:

user joins
user leaves
device appears
device disappears
network changes
demand increases
demand decreases
trust changes
state changes
capability becomes unavailable

Events may be local, distributed, delayed, duplicated, or reordered.

32. Policy

A Policy represents rules governing acceptable behavior.

Examples:

private data must execute only on trusted capabilities
critical state requires redundancy
battery-powered devices should avoid heavy computation
certain data must remain within a geographic boundary

Policies may originate from:

user
organization
application
system
legal requirements

Policy evaluation may therefore become part of adaptive placement.

33. Capability Contract

A Capability Contract describes what a capability provider promises to provide and under what conditions.

Potential properties include:

capability type
capacity
duration
availability
trust level
constraints
cost
revocation conditions

This is a candidate abstraction.

The project must determine whether explicit contracts are necessary or whether capabilities can be negotiated dynamically.

34. Logical Continuity

Logical Continuity represents preservation of the identity, authority, state, and required behavior of a logical entity while its physical execution changes.

For example:

Node A disappears
        ↓
Node B assumes responsibility
        ↓
logical service continues

This may be one of the most important properties that Adaptive Presence must eventually demonstrate.

35. Minimal Candidate Model

The above concepts may be reducible to a much smaller set.

A possible minimal model is:

Requirement
Capability
State
Identity
Authority
Presence
Communication
Constraint
Decision

Everything else may potentially emerge from combinations of these primitives.

This is only a hypothesis.

The project should actively attempt to reduce the model.

36. Primitive Reduction Test

A proposed primitive should survive questions such as:

Can the concept be expressed using another primitive?
Does removing it make the model impossible to describe?
Does it represent a genuinely distinct property?
Does implementation require it?
Does it simplify reasoning?
Can it be experimentally validated?

If a primitive fails these tests, it should be reconsidered.

37. No Primitive Is Sacred

The following terms are currently provisional:

Requirement
Intent
Capability
Capability Provider
Participant
Presence
Execution Responsibility
State
Authority
Identity
Trust
Constraint
Communication Path
Topology
Service
Placement
Adaptation
Migration
Replication
Reconciliation
Recovery
Availability
Demand
Resource
Computational Group
Logical Entity
Presence Transition
Decision
Observation
Event
Policy
Capability Contract
Logical Continuity

These names may change.

Some may merge.

Some may disappear.

New primitives may be discovered.

38. Fundamental Primitive Question

The central question of this document is:

What is the smallest conceptual vocabulary capable of describing adaptive computational presence without importing unnecessary assumptions from conventional infrastructure?

The answer must emerge from research and experimentation rather than from terminology alone.
