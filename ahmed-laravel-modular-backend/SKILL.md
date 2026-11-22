---
name: ahmed-laravel-modular-backend
description: Architect, build, and review secure modular Laravel backends using the project's Laravel version, current official documentation, and coordinated agent roles when available.
metadata:
  short-description: Modular Laravel backend engineering
---

# Ahmed Laravel Modular Backend

Deliver maintainable Laravel backend changes that fit the project, respect module boundaries, and follow documentation for the exact framework and package versions in use. Use this skill for Laravel APIs, domain modules, backend features, architecture changes, and technical reviews.

## 1. Establish project facts and documentation

- Inspect `composer.json`, `composer.lock`, the Laravel application bootstrap, existing module structure, routes, service providers, tests, and project instructions before choosing an implementation.
- Determine the installed Laravel and PHP versions from the project. Never assume that the latest framework release is the project's release.
- For version-sensitive behavior, verify against the official Laravel documentation for the installed major version at `https://laravel.com/docs/`. Use the official release notes and upgrade guide when release changes matter. For packages, use that package's official documentation and match the locked version.
- If Laravel Boost is installed and provides project-aware documentation search, use it to retrieve guidance for the installed Laravel and package versions. Cross-check critical or disputed behavior against official documentation.
- Do not claim that a source was checked if it was not available. If online documentation cannot be reached, inspect installed framework/package code and project conventions, then clearly flag any uncertain version-sensitive assumption.

## 2. Model modules around responsibilities

- First detect and follow the architecture already in use. Do not add a module framework or reorganize the application without a concrete need.
- When designing modules, group code around cohesive business capabilities or bounded contexts, not technical file types alone. Keep each module's public surface explicit.
- A module may own its routes, controllers, requests, resources, application services/actions, domain rules, models, migrations, policies, events, jobs, and provider/configuration where those fit the project.
- Keep dependencies pointed toward declared contracts or stable public interfaces. Avoid reaching into another module's internal models, repositories, migrations, or service classes. Use contracts, application APIs, or domain events for cross-module collaboration where appropriate.
- Do not create abstractions, repositories, DTO layers, or service classes by default. Add them when they protect a real boundary, simplify meaningful complexity, or match existing conventions.
- Treat schema ownership and data lifecycle as explicit module responsibilities. Review migration ordering, foreign keys, indexes, rollback behavior, and deployment compatibility before changing shared data.

## 3. Build Laravel features end to end

- Follow the installed Laravel version's idioms for routing, dependency injection, validation, authorization, Eloquent, serialization, queues, caching, events, and exception handling.
- Validate untrusted input at the boundary. Keep authentication, authorization, tenant scoping, and ownership checks explicit; validation alone is not authorization.
- Use policies/gates and form requests or the project's established equivalent. Return stable API resources and status/error shapes consistent with existing endpoints.
- Protect data integrity with database constraints and transactions where the operation spans related writes. Consider concurrency, retries, idempotency, and queue delivery semantics for asynchronous or payment-like workflows.
- Check query shape, eager loading, pagination, indexes, and transaction scope for data-heavy paths. Avoid hiding N+1 queries or expensive work behind convenience code.
- Keep secrets and environment-specific values in configuration; never commit credentials or expose them in logs or responses.

## 4. Include a security audit

For every non-trivial backend change, have the independent reviewer include a focused security pass. When the user asks for a security review, assess the requested scope systematically and report findings before proposing fixes. Begin by mapping the changed endpoints, assets, trust boundaries, identities, and tenant boundaries.

Check the concerns that apply to the feature:

- Authentication and session handling; authorization on every action and resource, including IDOR/BOLA and tenant isolation.
- Boundary validation, mass assignment, SQL/query injection, unsafe serialization, and sensitive fields exposed in API resources or logs.
- CSRF, CORS, cookie settings, and security headers for browser-facing flows; rate limits and abuse controls for public or expensive endpoints.
- File upload validation and storage access; SSRF risks from user-controlled URLs; webhook signature verification, replay protection, and idempotency.
- Transaction and concurrency behavior around permissions, balances, payments, and other security-sensitive state changes.
- Secrets management, error disclosure, audit logging, and relevant dependency advisories for the locked Composer dependencies.

Rank findings as Critical, High, Medium, or Low. For each finding, give the affected file/line or code path, a concrete impact or abuse scenario, evidence, and a focused remediation. Separate confirmed findings from assumptions and coverage limits; do not claim a clean audit beyond the code and checks actually reviewed. Keep the audit read-only unless the user requested remediation, and do not silently change authentication, CORS, rate limits, or permission policy outside the requested scope.

## 5. Run non-trivial backend work as a multi-agent workflow

For any non-trivial Laravel feature, module, refactor, migration, or security-sensitive change, coordinate multiple agents when the host exposes delegation. A simple question or tiny isolated fix does not need a team. The coordinating agent owns scope, shared contracts, integration, and the final result.

Use these distinct roles:

1. **Project and documentation researcher (read-only):** inspect the project structure and version pins; find the matching official Laravel and package documentation; report relevant files, constraints, source links, and version-sensitive details.
2. **Module architect (read-only):** map the domain boundaries, dependencies, data ownership, and integration points; propose the smallest coherent change and identify shared contracts before code is divided.
3. **Implementation agent:** implement one agreed vertical slice or module area. Give each editing agent exclusive ownership of its files; do not let workers independently change shared contracts, central routes, or the same migrations.
4. **Independent backend and security reviewer (read-only):** review the integrated diff for correctness, authentication/authorization, tenant boundaries, validation, injection, data exposure, webhook/upload/SSRF risks where relevant, data integrity, migration/deployment risks, query behavior, and versioned-doc mismatches. Return actionable findings with file references, severity, and evidence.

The researcher and architect can work in parallel. Start implementation after the coordinator reconciles their findings. Run the reviewer after integration; fix valid findings and re-review affected changes. Split implementation across workers only when the module boundaries are independent, and assign one owner for shared schema, contracts, and final integration.

Use the host's native delegation mechanism rather than assuming a particular agent API. On Antigravity, use subagents for focused research/review, `/swarm` for broad work that splits cleanly, and `/teamwork` only for large multi-milestone efforts. On Codex or another host, use its subagent tools when exposed. If the runtime cannot launch subagents, say so plainly and perform the same roles in separate sequential passes; never claim that multiple agents ran when they did not.

## 6. Validate changes proportionally

- Follow the user's requested validation scope and repository quality instructions. For backend behavior changes, identify the focused checks that provide useful evidence, such as relevant tests, static analysis, formatting, route inspection, or migration review; do not claim checks passed unless they ran.
- Cover meaningful behavior and failure paths when tests are part of the task: authorization, validation, persistence, module interactions, and expected responses. Avoid tests coupled only to private implementation details.
- Inspect generated diffs for accidental scope expansion, secrets, debug output, unsafe mass assignment, missing authorization, N+1 queries, and inconsistent module dependencies.
- Do not run destructive database commands, alter production data, or apply production migrations as part of ordinary implementation. Explain operational steps that require the user's environment or deployment process.

## 7. Handoff

Report the modules and boundaries changed, important documentation or version assumptions, security/data considerations, validation actually performed, and anything that needs follow-up. Keep the summary concise and tie claims to observable code or command output.
