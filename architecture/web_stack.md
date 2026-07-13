# Default Web Application Stack

This guidance applies to web applications built at RMI, that is: anything that serves a browser-based UI backed by a server-side API and database.

## The Default Stack

New web applications **should** use:

- **Frontend:** [React](https://react.dev/)
- **Backend / API:** [FastAPI](https://fastapi.tiangolo.com/) (Python)
- **Database:** [PostgreSQL](https://www.postgresql.org/)

This is a default, not a mandate. But the default exists for a reason: shared tooling, transferable knowledge across teams, easier code review, and lower onboarding cost enable better engineer fungibility across repositories.

## When to Deviate

Deviating from the default is allowed when there is a **strong, specific reason**, not a preference.

Examples of reasons that would justify a different choice:

- A hard technical constraint the default stack cannot meet (e.g., a data science workflow that fundamentally requires a different runtime, real-time requirements the default cannot satisfy, integration with a system that mandates a particular client library).
- An existing codebase or product being extended, where switching stacks would be more costly than living with the mismatch.
- A third-party or vendor requirement that dictates a particular framework or database.

Reasons that are **not** strong enough on their own:

- Personal familiarity or preference for a different framework.
- A newer framework being more exciting or trendy.
- Marginal performance differences at expected scale.

If you deviate, document the reason in the repository's `ARCHITECTURE.md` or equivalent so future maintainers understand the context.

## Suggested Adjacent Choices

Everything below are helpful suggestions for adjacent tooling.  **"If you have no idea where to start, start here"**. These are reasonable defaults that will not surprise anyone who has worked in another RMI web application. Deviate freely when you have a reason.

- **Python packaging & dependencies:** [`uv`](https://docs.astral.sh/uv/) — fast, lockfile-based, workspace support for monorepos.
- **Python lint & format:** [`ruff`](https://docs.astral.sh/ruff/).
- **Python test runner:** [`pytest`](https://docs.pytest.org/).
- **Database migrations:** [Alembic](https://alembic.sqlalchemy.org/).
- **Frontend build tool:** [Vite](https://vite.dev/).
- **Frontend test runner:** [Vitest](https://vitest.dev/).
- **Local development environment:** Docker Compose: one command brings up the database, API, and frontend together.

## Reference Implementation

[RMI/stitch](https://github.com/RMI/stitch) is a working example of this stack and the adjacent suggestions above. When starting a new web application, it is often faster to skim stitch's `README.md`, `ARCHITECTURE.md`, and root configuration files than to assemble the pieces from scratch.
[RMI/pbtar](https://github.com/RMI/pbtar) is a static web application that *has no server-side API or DB*. It does however follow the stack in the sense that the front-end is written in [React](https://react.dev/).
