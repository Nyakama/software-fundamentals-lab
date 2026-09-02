# Chapter 4: Pragmatic Paranoia

## Completion status

Draft notes for review.

Update this section after completing the chapter.

## Core themes to review

Chapter 4 focuses on building software with healthy caution.

The main areas to reflect on are:

- assuming mistakes can happen and designing accordingly;
- making expectations explicit between parts of a system;
- failing early when something impossible or unsafe happens;
- using assertions and checks to expose incorrect assumptions;
- managing resources carefully;
- avoiding overconfidence when working beyond what is currently known;
- building habits that make defects easier to detect and contain.

## Three important ideas

### 1. Make assumptions visible

Hidden assumptions are dangerous because they are difficult to test.

When code, documentation, or workflow depends on something being true, that
expectation should be made visible through validation, clear naming, checks,
tests, or documentation.

Reflection prompt:

- What assumption in one of my current projects could cause confusion or failure
  if it is not written down or checked?

### 2. Fail clearly instead of hiding problems

A confusing failure can waste more time than the original bug.

When a system reaches a state that should not happen, the problem should be
reported clearly enough for someone to understand what went wrong and where to
look next.

Reflection prompt:

- Where do my current projects silently ignore errors, return vague messages, or
  continue after something important has failed?

### 3. Manage resources responsibly

Resources such as files, connections, sessions, memory, credentials, and time
should be handled deliberately.

A pragmatic developer should know when a resource is opened, who owns it, how it
is released, and what happens if the operation fails halfway through.

Reflection prompt:

- Which resource in a current project needs clearer ownership, cleanup, or error
  handling?

## Two possible applications

### 1. Add one visible safety check

Choose one current project and find an assumption that should be checked.

Examples could include:

- validating required environment variables;
- checking required request fields before processing;
- confirming file existence before reading;
- handling missing database records clearly;
- preventing an invalid workflow status transition;
- improving an unclear error message.

Action:

- identify the assumption;
- decide the safest place to check it;
- add or document the check;
- confirm that the failure message helps future debugging.

### 2. Review one resource lifecycle

Choose one area where a resource is opened, created, reserved, uploaded,
connected, or stored.

Review:

- where the resource is created;
- who owns it;
- when it is released or cleaned up;
- what happens if the operation fails;
- whether the current behaviour is visible in logs, tests, or documentation.

Action:

- fix one small resource-handling issue; or
- create a tracked note explaining the risk and recommended next step.

## Remaining question

How do I balance defensive programming with keeping the code simple and easy to
read?

## Working answer

Defensive programming is useful when it protects important assumptions,
security boundaries, data integrity, or difficult-to-debug workflows.

It becomes harmful when every small possibility creates noisy checks that make
the main logic harder to understand.

A good balance is to defend the boundaries, validate important assumptions, fail
clearly, and keep the normal path readable.

## Personal takeaway

Pragmatic paranoia is not fear-based development.

It is disciplined caution. The goal is to make incorrect assumptions, unsafe
states, and resource problems visible before they become larger failures.

## Follow-up actions

- [ ] Identify one hidden assumption in a current project.
- [ ] Add or document one safety check.
- [ ] Review one resource lifecycle.
- [ ] Review these notes after completing the chapter.
