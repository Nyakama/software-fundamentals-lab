# Chapter 6: Concurrency

## Completion status

Draft notes for review.

Update this section after completing the chapter.

## Core themes to review

Chapter 6 focuses on thinking about work that happens independently, overlaps in
time, or depends on coordination between separate activities.

The main areas to reflect on are:

- identifying work that can happen independently;
- reducing unnecessary waiting between steps;
- separating workflow from timing;
- understanding the risks of shared state;
- designing safer coordination between tasks;
- recognising race conditions and timing-related bugs;
- using queues, events, background jobs, or services where appropriate;
- making concurrent behaviour observable and easier to debug.

## Three important ideas

### 1. Concurrency is about independence, not just speed

Concurrency is not only about making software faster.

It is also about recognising which parts of a process do not need to block each
other. When independent work is separated well, the system can become easier to
scale, easier to reason about, and more responsive.

Reflection prompt:

- In one current project, which tasks are unnecessarily waiting for each other
  even though they could be separated?

### 2. Shared state creates risk

When multiple parts of a system can read or change the same information at the
same time, bugs can become difficult to reproduce.

A pragmatic developer should be careful with shared data, temporary files,
sessions, caches, background jobs, and database records that can be updated from
more than one place.

Reflection prompt:

- Where in my current projects could two users, jobs, or processes update the
  same data in a way that causes confusion or incorrect results?

### 3. Timing problems need visibility

Bugs caused by timing, ordering, or coordination are often hard to debug.

Clear logging, simple state transitions, idempotent operations, and careful
error handling make concurrent workflows easier to understand when something
goes wrong.

Reflection prompt:

- Which workflow in a current project would be difficult to investigate if a
  background step, email, upload, or status update failed halfway through?

## Two possible applications

### 1. Find one unnecessary blocking workflow

Review one current project and identify a process where one step blocks another
step unnecessarily.

Examples could include:

- sending email inside a request before returning a response;
- waiting for a slow report before saving user input;
- doing heavy processing during page load;
- requiring manual steps that could be queued or tracked;
- combining user interaction, calculation, storage, and notification in one
  fragile flow.

Action:

- identify the blocking step;
- explain what is waiting and why;
- decide whether the step should stay synchronous, become asynchronous, or be
  documented as a future improvement.

### 2. Review one shared-state risk

Choose one area where data can be changed by more than one user, request, job,
or process.

Review:

- what data is shared;
- who or what can change it;
- what could happen if two changes occur close together;
- whether the current system prevents duplicate or conflicting updates;
- whether failures are visible enough to debug.

Action:

- add a small note, test, guard, or tracked issue for the risk;
- avoid broad refactoring unless tests already exist.

## Remaining question

How do I decide when concurrency is worth adding versus when it creates
unnecessary complexity?

## Working answer

Concurrency is useful when it removes real waiting, improves responsiveness,
protects user experience, supports scale, or separates work that is genuinely
independent.

It becomes unnecessary complexity when the workflow is simple, the performance
gain is unclear, the shared-state risks are not understood, or the team cannot
debug the behaviour reliably.

A good balance is to first make the workflow clear, identify the independent
parts, protect shared state, and only then introduce concurrency where it solves
a real problem.

## Personal takeaway

Concurrent systems require discipline.

The goal is not to make everything happen at the same time. The goal is to
separate independent work safely, reduce unnecessary waiting, and make timing
problems visible before they become hidden failures.

## Follow-up actions

- [ ] Identify one unnecessarily blocking workflow in a current project.
- [ ] Review one shared-state risk.
- [ ] Decide whether one task should remain synchronous or become asynchronous.
- [ ] Review these notes after completing the chapter.
