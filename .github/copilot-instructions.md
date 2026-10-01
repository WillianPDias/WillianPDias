# GitHub Copilot Instructions

## Context

This repository represents the GitHub profile and engineering workspace of Willian Dias.

## Engineering principles

- Prefer simple, explicit and maintainable solutions.
- Favor composition over inheritance.
- Keep modules cohesive and responsibilities narrowly scoped.
- Avoid hidden side effects and unnecessary global state.
- Make failure modes explicit and observable.
- Preserve backward compatibility unless a breaking change is intentional and documented.

## Code quality

- Use descriptive names and small functions.
- Prefer typed interfaces and explicit contracts.
- Avoid duplication when a shared abstraction is stable and justified.
- Do not introduce abstractions speculatively.
- Add or update tests for behavior changes.
- Treat warnings, static-analysis findings and lint errors as defects unless explicitly waived.

## Security

- Never hard-code credentials, API keys, tokens, passwords or private endpoints.
- Read secrets from environment variables or a dedicated secret manager.
- Do not log secrets or complete authorization headers.
- Validate external input at trust boundaries.
- Apply least privilege to credentials, tokens and integrations.
- Prefer short-lived credentials and token rotation where supported.
- Flag potentially destructive, irreversible or security-sensitive changes before implementation.

## AI and LLM integrations

- Keep provider-specific code behind adapters or provider interfaces.
- Separate model routing from business logic.
- Prefer configuration-driven selection of providers and models.
- Make timeout, retry, fallback and rate-limit behavior explicit.
- Do not silently fall back to another model when this can change semantics, privacy or cost.
- Never place provider tokens in source code or committed configuration.
- For Ollama, NVIDIA NIM and cloud model providers, normalize requests and responses at the integration boundary.
- Capture useful telemetry without persisting prompts, secrets or sensitive payloads by default.

## Architecture

For multi-provider LLM systems, prefer this logical separation when applicable:

1. Application / client layer
2. Orchestration and model-routing layer
3. Provider adapter layer
4. Configuration and policy layer
5. Observability layer
6. Secret-management boundary

## Pull requests

- Keep PRs focused on one coherent change.
- Explain why the change is needed, not only what changed.
- Document risks, migration impact and rollback strategy when relevant.
- Mention security implications and new external dependencies.

## Documentation

- Keep examples runnable and synchronized with implementation.
- Use Brazilian Portuguese for user-facing project documentation unless the project explicitly adopts English.
- Use English for code identifiers, APIs and technical protocol names unless an existing codebase convention says otherwise.
