---
type: Principle
title: SSD Verification Principles
description: Foundational rules that distinguish device verification from protocol demonstration.
tags: [prove, icet, ssd, verification, resilience]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: test-execution-qualification-directive-2026-08-02
    resource: /sources/test-execution-qualification-directive-2026-08-02.md
    title: PROVE leader Test execution qualification directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Principles

## Verify the Device, Not Only the Specification

The Test Platform exists to validate an NVMe SSD device. NVMe, OCP, customer, and internal specifications supply requirements, but none alone defines the platform's complete verification capability.

## Negative Behavior Is Valid Test Intent

Reset, power interruption, malformed or adverse sequences, error injection, and destructive state transitions may be required test behavior. The platform must not classify them as forbidden merely because they are operationally hazardous.

## The Platform Must Retain Control

For any technically supported verification action, IceT must retain execution control and Evidence through Reset, injected Error, and abnormal Device state, then continue, recover, or terminate deterministically. This is a Platform invariant rather than an optional property of an individual Test. Loss of IceT control must not be mislabeled as poor Test generation.

## Stable Core, Generated Feature Logic

The platform should provide reliable low-level primitives and an abstract command-transfer capability. Feature-specific test logic should be expressible in generated Test Cases so missing high-level platform APIs do not become the primary expansion bottleneck.

## Observable Evidence

Every verdict must be supported by the commands, device state, environment state, logs, expected results, and recovery actions that produced it.

# Capability Boundary

IceT is expected to support pyNVMe-class control except direct generation of PCIe TLP packets. It also has access to internal sideband control and driver-level memory mapping capabilities. Exact supported primitives belong in the IceT repository.
