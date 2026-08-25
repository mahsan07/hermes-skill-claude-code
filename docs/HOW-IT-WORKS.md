# How Claude Code Works

The visuals on this page are static SVGs, so they render directly on GitHub on phones and desktop browsers. Each one is generated from a model specific to this skill.

## System architecture

![Detailed system map for Claude Code](../assets/system-map.svg)

### Components

- **1. Bounded coding request:** participates in define files behavior and stop conditions.
- **2. Repository instructions:** participates in provide repository-local instructions.
- **3. Claude Code session:** participates in delegate the bounded implementation.
- **4. Local diff and tests:** participates in inspect the resulting diff.
- **5. Human review gate:** participates in run independent tests and checks.

## Actor and data sequence

![Actor and data sequence for Claude Code](../assets/operation-sequence.svg)

### 1. Define files behavior and stop conditions

**Primary surface:** `Bounded coding request`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.
### 2. Provide repository-local instructions

**Primary surface:** `Repository instructions`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.
### 3. Delegate the bounded implementation

**Primary surface:** `Claude Code session`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.
### 4. Inspect the resulting diff

**Primary surface:** `Local diff and tests`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.
### 5. Run independent tests and checks

**Primary surface:** `Human review gate`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.
### 6. Return changes for human review

**Primary surface:** `Bounded coding request`

Record the concrete input, the operation performed, and the evidence produced at this stage. Continue only when the output is sufficient for the next stage; otherwise preserve the blocker and stop.

## Example output shape

![Illustrative output for Claude Code](../assets/example-output.svg)

The example is a visual contract: a real run may look different, but it should expose comparable state, provenance, and verification information. It is not presented as evidence of a live external action.

## Decision and stop conditions

![Decision guide for Claude Code](../assets/decision-guide.svg)

The workflow stops when the target is ambiguous, the relevant surface is unavailable or unauthorized, or the final artifact cannot be checked. A logged-in session or successful tool call is not by itself proof that the requested outcome is complete.

## Verification checklist

- Confirm every component shown in the system map exists in the target environment.
- Trace the actor sequence using actual tool output or artifact state.
- Compare the result with the example-output information contract.
- Re-read or reopen the final artifact instead of trusting an attempt message.
- Report omitted stages, unsupported capabilities, and remaining human decisions.
