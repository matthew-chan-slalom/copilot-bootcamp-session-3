# Product Requirements Document (PRD) - TODO App Upgrade

## 1. Overview

This PRD defines the confirmed scope for upgrading the existing TODO app, which currently supports only a task title and completed status. Based on the attached requirements meeting and Slack follow-up, the upgrade is intended to make the app more useful while keeping the MVP simple and teachable. The confirmed MVP focuses on due dates, priority levels, date-based filtering, and local-only storage with no backend changes. Items explicitly moved to Post-MVP or confirmed as out of scope are listed separately below.

## 2. MVP Scope

- Add an optional `dueDate` field to each task.
- Store `dueDate` in ISO `YYYY-MM-DD` format.
- Add a `priority` field with allowed values `P1`, `P2`, and `P3`.
- Default `priority` to `P3`.
- Keep `title` as a required field.
- Ignore invalid `dueDate` values and treat them as absent.
- Add filter views for `All`, `Today`, and `Overdue`.
- In the `All` view, include completed tasks.
- In the `Today` and `Overdue` views, show only incomplete tasks.
- Keep storage local only.
- Do not make backend or external storage changes.

## 3. Post-MVP Scope

- Visually highlight overdue tasks.
- Add sorting so tasks are ordered by overdue status first, then priority from `P1` to `P3`, then due date ascending, with tasks that have no due date listed last.

## 4. Out of Scope

- Notifications
- Recurring tasks
- Multi-user support
- Keyboard navigation
- External storage