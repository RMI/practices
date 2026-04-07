# Agile Overview

Agile is a way to deliver better products through small increments, fast feedback, and clear ownership. These concepts work regardless of whether a team is using post-it notes, GitHub issues, Linear or Jira.

## tl;dr

- optimize for outcomes, not outputs
- work in small, testable increments
- keep the backlog ready and prioritized
- use sprint goals to focus the team
- inspect and adapt every sprint

## Why This Leads to Better Products

Strong agile practice reduces delivery risk by shortening feedback loops. It helps teams learn earlier, change direction faster, and avoid spending weeks building the wrong thing.

## Operating Principles

- Outcome driven: deliver work that advances product goals.
- Small batches: prefer slices that can be built, reviewed, and learned from quickly.
- Fast feedback: get stakeholder and user input early and often.
- Shared ownership: product, engineering, and delivery leads all shape success.
- Continuous improvement: carry a small number of lessons from one sprint into the next.

## Roles

- Product Manager / Product Owner: owns product outcomes, backlog priority, and PRD alignment.
- Tech Lead: shapes technical approach, feasibility, and sequencing.
- Scrum Lead: facilitates cadence, surfaces blockers, and protects healthy flow.
- Engineering Team: estimates, commits, builds, tests, and demos.
- Stakeholders / SMEs: provide feedback and domain context.

These roles are not always separate people, but it is important that the PM/PO is distinct from the development/engineering team, so that the project stays focused on product outcomes, rather than technical ones. At RMI, the "scrum lead" will almost alway be either the PM/PO or Tech Lead.

## Delivery Flow

Recommended states:

- Backlog
- Selected for Development
- In Progress
- In Review
- Done

The important rule is not the exact labels. The important rule is that work should move through a small, visible set of states with clear entry criteria.

## Link To Strategy

Use this chain:

`OKRs -> PRDs -> epics/stories -> sprint goals`

See [OKRs](/Users/jhoffart/github/practices/process/okrs.md) for guidance on defining outcomes.

## Good Sprint Goals

A strong sprint goal:

- is one or two sentences
- describes the outcome of the sprint
- connects to a PRD, milestone, or key result
- helps the team make tradeoffs during the sprint

Anti-pattern: Weak sprint goals are just a list of tickets.

## Good Tickets

A ticket is ready when it has:

- clear user or business value
- enough context to start
- acceptance criteria
- known dependencies, blockers or constraints
- a size that fits inside a single sprint

If the ticket is too large to close entirely in a single sprint (e.g. for code-work, closed with a single right-sized PR), then the ticket should be split before bringing it into sprint.

## Working Agreements

- prefer small PRs and review them within 24 business hours
- document decisions in shared channels
- keep acceptance criteria current when scope changes
- account for capacity, support load, and time off before committing work

## Practical Rule

If the team cannot explain why a ticket matters, what done looks like, and how it supports a larger product goal, it is not ready.
