# Chapter 2: A Pragmatic Approach

## Completion status

Draft notes for review.

Update this section after completing the chapter.

## Core themes to review

Chapter 2 focuses on practical habits for building software deliberately rather
than accidentally.

The main areas to reflect on are:

- designing for change;
- avoiding duplicated knowledge;
- keeping components independent where possible;
- using small working slices to reduce uncertainty;
- learning through prototypes and experiments;
- using language and naming carefully;
- improving estimates through practice and feedback.

## Three important ideas

### 1. Avoid duplicating knowledge

Repeated knowledge creates maintenance risk.

When the same rule, decision, calculation, or explanation exists in multiple
places, future changes become harder because every copy must be found and kept
consistent.

Reflection prompt:

- Where in my current projects am I repeating the same business rule,
  explanation, SQL logic, configuration, or documentation?

### 2. Build systems that can change

Good design reduces the cost of change.

A useful system should not require large rewrites every time a requirement
changes. Clear boundaries, simple interfaces, and focused modules make future
changes safer.

Reflection prompt:

- Which part of one current project would be difficult to change because too
  many things depend on it?

### 3. Reduce uncertainty with small experiments

A small working slice can teach more than a large plan.

When a requirement, technology, integration, or design choice is uncertain, a
small prototype or tracer implementation can expose risks early.

Reflection prompt:

- What is one uncertain area in a current project that could be tested with a
  small experiment before committing to a full implementation?

## Two possible applications

### 1. Find one duplicated piece of knowledge

Review one active repository or document set and identify one example of
duplicated knowledge.

Examples could include:

- repeated setup instructions;
- copied validation rules;
- duplicated SQL logic;
- repeated environment variable explanations;
- repeated wording across user manuals;
- repeated project assumptions.

Action:

- either remove the duplication;
- or document which location should be treated as the source of truth.

### 2. Use a small experiment before a larger change

Before starting a risky feature or refactor, define a small experiment that can
answer one important question.

The experiment should answer:

- What are we trying to learn?
- What is the smallest useful test?
- What result would give confidence?
- What result would make us change direction?

## Remaining question

How do I decide when to refactor duplicated or tightly coupled code immediately
versus simply documenting the risk and returning to it later?

## Working answer

A design issue should usually be fixed sooner when it affects correctness,
security, repeated development work, or future changes that are already likely.

It may be acceptable to document and defer the issue when the risk is small,
the affected area is stable, and there is a clear source-of-truth note or
tracked follow-up.

The key is to make the trade-off visible instead of silently leaving confusion
for the next person.

## Personal takeaway

A pragmatic approach is not only about writing code. It is about reducing
avoidable confusion.

Good software work should make important knowledge easier to find, change, test,
and explain.

## Follow-up actions

- [ ] Identify one duplicated piece of knowledge in a current project.
- [ ] Decide which version should become the source of truth.
- [ ] Identify one area where a small prototype would reduce uncertainty.
- [ ] Review these notes after completing the chapter.
