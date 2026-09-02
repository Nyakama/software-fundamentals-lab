# Chapter 5: Bend, or Break

## Completion status

Draft notes for review.

Update this section after completing the chapter.

## Core themes to review

Chapter 5 focuses on designing software that can change without breaking.

The main areas to reflect on are:

- reducing coupling between parts of a system;
- avoiding unnecessary dependencies;
- keeping responsibilities clear;
- designing flexible interfaces;
- preferring composition and small cooperating parts where appropriate;
- avoiding rigid structures that make future change expensive;
- making configuration and policy easier to adjust;
- recognising when a design is becoming fragile.

## Three important ideas

### 1. Flexible systems need low coupling

When too many parts of a system know too much about each other, change becomes
dangerous.

A small change in one place can create unexpected work elsewhere. A more
flexible design keeps knowledge local, reduces unnecessary connections, and
makes each part easier to understand.

Reflection prompt:

- Which part of one current project would be risky to change because too many
  other files, rules, or workflows depend on it?

### 2. Clear boundaries make change safer

A useful boundary separates responsibilities.

When a component has a clear purpose and communicates through a simple interface,
it becomes easier to test, replace, improve, or reuse. When boundaries are vague,
logic spreads across the system and becomes harder to control.

Reflection prompt:

- Where in my current work is business logic mixed into places where it does not
  clearly belong, such as views, controllers, scripts, or copied documentation?

### 3. Design should leave room for future decisions

Not every future requirement can be predicted.

The goal is not to over-engineer for every possibility. The goal is to avoid
locking the system into choices that are likely to change. Good design keeps
important decisions visible and avoids making the easy path fragile.

Reflection prompt:

- Which decision in a current project feels too hard-coded, too hidden, or too
  expensive to change later?

## Two possible applications

### 1. Identify one fragile dependency

Review one active project and find one area where a small change could have a
large ripple effect.

Examples could include:

- repeated route names;
- hard-coded URLs;
- duplicated role or permission checks;
- copied scoring or calculation rules;
- configuration values embedded directly in code;
- views that contain business decisions;
- scripts that depend on a specific local machine setup.

Action:

- identify the dependency;
- explain why it is fragile;
- decide whether to fix it now, document it, or create a tracked follow-up.

### 2. Improve one boundary

Choose one small area where responsibilities can be made clearer.

Possible improvements:

- move repeated constants into one source-of-truth file;
- document which file owns a business rule;
- separate display wording from calculation logic;
- improve naming so responsibilities are easier to understand;
- add a small test around a behaviour before changing it;
- create a short architecture note explaining an important boundary.

Action:

- make the smallest useful improvement;
- avoid broad refactoring without tests;
- record what changed and why.

## Remaining question

How do I make software flexible enough for change without over-engineering it
for imagined future requirements?

## Working answer

A flexible design should protect the areas most likely to change, especially
business rules, configuration, integrations, permissions, calculations, and
external workflows.

Over-engineering happens when complexity is added for possibilities that are
unclear, unlikely, or not connected to a real decision.

A good balance is to keep the current solution simple, avoid unnecessary
coupling, make important decisions visible, and design boundaries that allow
future change without requiring a rewrite.

## Personal takeaway

Software breaks when change has nowhere safe to go.

A pragmatic developer should not try to predict every future requirement, but
should design systems so that reasonable change is possible without panic,
guesswork, or widespread damage.

## Follow-up actions

- [ ] Identify one fragile dependency in a current project.
- [ ] Decide whether it should be fixed, documented, or tracked.
- [ ] Improve one small boundary between responsibilities.
- [ ] Review these notes after completing the chapter.
