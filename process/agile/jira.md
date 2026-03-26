# Jira Runbook

This document explains how to implement the agile operating model in Jira. The goal is not perfect Jira hygiene. The goal is clear, visible delivery.

## tl;dr

- use Jira to make priorities, ownership, and status visible
- keep workflows simple
- make tickets ready before sprint planning
- keep sprint goals explicit
- capture feedback as backlog items, not scattered notes

## Recommended Structure

Suggested issue hierarchy:

- Epic: a meaningful body of work tied to a PRD, milestone, or outcome
- Story: a sprint-sized unit of work
- Bug: a defect that needs triage and delivery

## Recommended Workflow

Suggested statuses:

- Backlog: captured work that is not yet ready or prioritized for an upcoming sprint
- Selected for Development: prioritized work with enough context and acceptance criteria to bring into planning
- In Progress: work actively being implemented
- In Review: work believed to meet acceptance criteria and awaiting review, demo, or approval
- Done: reviewed work that has been accepted and does not need more delivery work in the current cycle

## Sprint Setup

Before starting a sprint:

- confirm the backlog is prioritized
- make sure selected tickets have acceptance criteria
- account for time off, support load, and known dependencies
- draft the sprint goal before the planning meeting

At sprint start:

- create the sprint
- add the committed issues
- set the sprint goal in Jira

## Writing Good Jira Tickets

Each ticket should include:

- a concise outcome-focused title
- user or business context
- acceptance criteria
- story point estimates
- relevant links to PRDs, designs, or technical notes
- clear ownership when work begins

Good tickets reduce clarification churn during the sprint.

## Acceptance Criteria

Acceptance criteria should describe what proves the work is done.

Good acceptance criteria are:

- specific
- testable
- understandable by both product and engineering

Avoid acceptance criteria that are only implementation notes.

## Board Hygiene

- do not pull work into a sprint unless it is ready
- keep ticket status current
- split oversized tickets instead of carrying ambiguity forward
- capture review feedback in Jira when it changes scope or priority
- close the sprint with clear decisions on incomplete work

## Sprint Review In Jira

After review:

- move accepted work to Done
- move incomplete work to the correct active state
- create follow-up tickets from stakeholder feedback
- update priorities before the next planning cycle

## Atlassian Goals Note

If your team uses Atlassian Goals for OKRs, use it as the outcome layer above Jira delivery work. Goals should describe the intended result; Jira issues and sprints should show the work advancing that result. Keep the linkage visible, but do not replace good OKRs with a long list of Jira tickets.
