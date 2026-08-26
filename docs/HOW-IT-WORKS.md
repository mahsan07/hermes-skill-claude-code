# How Claude Code Works

Delegate bounded coding tasks to Claude Code CLI with explicit scope and review gates.

![Detailed systems blueprint for Claude Code](../assets/system-blueprint.png)

## Stages

### 1. Define files behavior and stop conditions

**Primary surface:** `Bounded coding request`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 2. Provide repository-local instructions

**Primary surface:** `Repository instructions`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 3. Delegate the bounded implementation

**Primary surface:** `Claude Code session`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 4. Inspect the resulting diff

**Primary surface:** `Local diff and tests`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 5. Run independent tests and checks

**Primary surface:** `Human review gate`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 6. Return changes for human review

**Primary surface:** `Human review gate`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.

## Failure handling

- **Authorization failure:** do not probe credentials or broaden access; report the missing authority.
- **Target ambiguity:** stop before mutation and request the minimum identifying information.
- **Tool or service failure:** retain error evidence, retry only safe transient failures, and cap retries.
- **Verification failure:** classify the run as incomplete even when the preceding operation returned success.

## Completion evidence

The handoff should contain the original request, inspection state, preview or plan, exact execution result, direct verification, and a final receipt naming limitations and withheld actions.
