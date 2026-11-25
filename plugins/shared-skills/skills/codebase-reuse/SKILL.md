---
name: codebase-reuse
description: Use before non-trivial implementation work to find, trace, and reuse existing code across any repository. Avoid when the task is a trivial one-file edit or the user explicitly asks for a from-scratch rewrite.
---

# Codebase Reuse

Use this skill before non-trivial code changes. Keep the investigation proportional to risk: targeted searches and relevant files first, broader indexing or docs only when they save context or clarify structure.

## Workflow

1. Identify the feature area, entry points, and likely owners from the request, project instructions, manifests, and targeted search.
2. Search for existing implementations of the requested behavior and nearby names, routes, components, commands, services, hooks, clients, DTOs, types, validation, constants, business rules, state, and persistence logic.
3. Trace the relevant data flow far enough to understand callers, callees, side effects, and verification points.
4. Prefer, in order: reuse existing implementation, extend existing implementation, reuse an existing abstraction, then create new code only when necessary.
5. Before editing, briefly report the existing relevant code, reusable code, missing functionality, and proposed minimal implementation.
6. Implement the smallest correct change, following local patterns and project-specific instructions.
7. Verify with the narrowest check that would catch a real breakage; broaden only for shared or high-risk behavior.

## Constraints

- Do not duplicate existing functionality without a concrete reason.
- Do not refactor unrelated code, add speculative abstractions, add unnecessary dependencies, or rewrite working code without a requirement.
- Do not scan entire repositories when targeted searches, project docs, or an index can answer the question.
- Use repository indexing or graph tools when they answer structural questions more cheaply than repeated file reads.
- Use external documentation only when repository evidence is insufficient or library behavior/version details need verification.
- Keep summaries concise and avoid re-reading unchanged files already understood in the current task.

## Scale

For simple mechanical edits, use normal local context and skip the report. For larger or ambiguous changes, expand investigation until the reuse decision is evidence-based, then stop.
