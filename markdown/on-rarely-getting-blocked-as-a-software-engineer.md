---
title: "Why strong engineers are rarely blocked"
description: "What experienced engineers do differently when the work gets difficult, uncertain, or dependent on someone else."
category: "Engineering"
date: "2026-08-23"
---

A pattern becomes visible after watching engineers work for long enough: the strongest engineers are not the ones who never get blocked. They are the ones who spend very little time staying blocked.[^1] 

[^1]: This observation is informed by recurring patterns in engineering teams: how people handle uncertainty, dependencies, reviews, and organizational constraints.

Earlier in their career, an engineer might wait for an answer, a review, a migration, or a meeting before doing anything else. The task in front of them becomes the only task, and when it stops moving, the entire day stops with it. Over time, that habit changes. They learn that being blocked is sometimes unavoidable—but remaining helplessly blocked usually is not.

## Sometimes it is a skill issue

The obvious kind of blocker is a knowledge gap. An engineer may not know how to implement a rate limiter, understand an unfamiliar service, or configure a development environment that has accumulated years of institutional memory.

The answer is not to pretend to know. Strong engineers ask better questions, find the right person, read the relevant code, and learn quickly enough to move forward. They turn a vague request for help into something concrete:

> “I tried A and B. The request reaches service X, but fails before it writes to Y. Is there an assumption about Z that I’m missing?”

That kind of question is easier to answer and teaches the engineer something reusable. Knowledge reduces many blockers, but it cannot remove all of them. A database team may still need a week to approve a migration. An external dependency may still be unavailable. Technical ability does not repeal organizational time.

## Keeping more than one piece of work moving

One of the most useful habits observed in effective engineers is that they rarely have only one thing in motion.

They do not respond to a blocked task by filling the day with meaningless chores. Instead, they keep a small number of tasks alive—usually one important task and one lower-priority task that can be paused without causing damage.

The exact number varies with the workload. Sometimes there are two tasks; occasionally there are four or five. More than that creates unnecessary context switching, but one is too few. If the only task is blocked, the engineer has accidentally made someone else’s delay their entire schedule.

The important distinction is priority. Only one task should usually be treated as the highest-priority commitment. If two urgent tasks arrive at once, a strong engineer makes the conflict visible instead of quietly trying to satisfy both. A conversation with their manager can prevent a week of invisible thrashing.

A simple, explicit priority list does more work than most people expect. It tells the engineer what to pick up next, gives their manager a chance to correct assumptions, and makes it easier to put a task down when the original work becomes unblocked.

## Not asking the organization for the impossible

Some blockers are created by insisting on a solution that the organization is not prepared to support.

An engineer may decide that a new feature must use Memcached even though every team around the company uses Redis. They then spend days persuading infrastructure teams, writing proposals, waiting for approvals, and explaining the same decision in different meetings. The work is described as being “blocked on Memcached,” but the deeper problem is that the engineer has chosen a path with no realistic route to completion.

The stronger engineer notices the constraint and chooses Redis. The feature ships. If Memcached still represents a genuinely important capability, that conversation can happen separately, with its own scope and priority.

This is not an argument for accepting every bad technical decision. Sometimes changing the organization is the highest-value work. But it is rarely useful to confuse a long political campaign with the delivery of the current project. Strong engineers know which fight serves the mission and which fight merely delays it.

## Anticipating blockers before they arrive

Experienced engineers develop a map of organizational friction.

They know which services take six months to create, which teams review changes slowly, which approval processes are formal in name but informal in practice, and which systems are safe to extend without a meeting. That knowledge changes how they design projects.

If creating a new service takes half a year, an engineer may first look for a way to use an existing service. If an edge-networking change is likely to trigger weeks of review, the design may avoid that dependency. This is not always elegant architecture, but it can be the difference between a project that takes one month and one that takes one year.

There is an uncomfortable side effect: strong engineers often learn to route around dysfunction rather than repair it. That may not be healthy for the company in the long run, but when an important project is at risk, shipping the project can be the responsible choice. The organizational problem can be documented and addressed later—provided someone remembers to do so.

## Sequencing the risky work first

When a task has a high chance of being blocked, it should usually be started early.

A database migration is a simple example. If the database team must review and run it, the migration can be submitted before the backend code is finished. While the migration is being reviewed, the engineer can write and test the code that depends on it.

The same principle applies to permissions, API contracts, security reviews, legal approvals, and cross-team dependencies. The riskiest piece of work should not be left until the end, when every other part of the project is waiting on it.

This requires judgment. If an engineer does not yet understand the migration, putting it up early may create more confusion than progress. But with enough planning, many “future blockers” can be converted into parallel work.

## Asking for help without surrendering ownership

A lesson many engineers learn late is that asking for help is not a failure of independence.

A manager and a skip-level manager often have something the engineer does not: the organizational authority to make a stuck dependency important to another team. A message that receives no response can suddenly become a scheduled conversation when the right manager asks why the work is waiting.

The engineer still owns the technical problem. Management supplies leverage.

This kind of escalation should be used carefully. Asking for intervention on every obstacle suggests that the engineer cannot navigate ordinary disagreements. Escalating a technical misunderstanding can also make the person doing the escalation look careless. But when a high-priority project is genuinely blocked by another team, keeping silent is not maturity. It is simply hiding the risk.

The best escalation is specific. It explains what has been tried, what is needed, why the dependency matters, and what decision would allow the work to continue. It asks for leverage, not rescue.

## What strong engineers do differently

Strong engineers still encounter blocked tickets. They wait for code reviews, approvals, answers, credentials, migrations, and decisions. The difference is that they do not let one immovable object become the shape of their entire workday.

They build knowledge so fewer problems are mysterious. They keep a second piece of work available. They choose realistic paths through organizational constraints. They identify dependencies early and sequence work around them. And when a blocker genuinely requires authority beyond their reach, they ask for help before the delay becomes a surprise.

Being unblocked is not a personality trait. It is a collection of habits—technical, organizational, and occasionally political. The engineers who appear unusually calm during difficult projects have often learned to practice those habits long before the crisis becomes visible.

That is why strong engineers are rarely blocked: not because the work gives them fewer obstacles, but because they are better at turning obstacles into information, parallel work, a different decision, or a timely request for help.

---

*When “blocked” means anything from waiting on a code review to having no idea how to proceed, the solution is rarely to wait passively. The next move is usually available—it just may not be the move originally planned.*

<!-- Source note: rewritten from observed engineering patterns and supplied reference material. -->

