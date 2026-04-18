# Solmu — Autonomous Resilience & Chaos Engineering Motor

## Project Overview

**Solmu** is an autonomous, single-binary tool for unified Stress/Load Testing and Chaos Engineering, driven by AI-powered Architecture Decision Records (ADRs). It combines extreme efficiency on ARM architectures with reactive, high-contrast interfaces.

---

## Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Backend/Daemon** | Rust (Axum, Tokio, Clap) | Load generation, network interception, CLI |
| **Frontend** | Leptos (SSR + WASM) | Reactive dashboard with Signals, no JS toolchains |
| **Messaging** | NATS (Embedded) | Event bus for chaos events and coordination |
| **Persistence** | SurrealDB (Embedded) | Event logs, chaos history, traces |
| **Observability** | OpenTelemetry (OTLP) | Performance degradation ingestion & analysis |
| **Intelligence** | Gemini API | Test planning (Architect), post-mortem analysis |
| **Design System** | W3C Design Tokens | High-contrast UI optimized for dense grids |

---

## Project Structure

```
solmu/
├── CLAUDE.md              # This file
├── README.md              # Product vision & tech stack
├── LICENSE
├── Cargo.toml             # Rust workspace
│
├── crates/
│   ├── solmu-cli/         # CLI entry point
│   ├── solmu-daemon/      # Core daemon (load gen, network interception)
│   ├── solmu-agent/       # AI-driven test planner & ADR generator
│   └── solmu-observability/  # OpenTelemetry integration
│
├── web/
│   ├── app/               # Leptos SSR + WASM app
│   └── design-system/     # W3C design tokens & components
│
├── .github/
│   └── workflows/         # CI/CD (lint, test, build, deploy)
│
└── docs/
    ├── architecture.md    # System design & data flow
    ├── adr/               # Architecture Decision Records
    └── phase-*.md         # Phase-specific documentation
```

---

## Development

### Setup
```bash
cargo install cargo-leptos
cargo build
```

### Running
```bash
# Start daemon + dashboard
cargo run --bin solmu-cli -- daemon

# Run a resilience test
solmu test --config examples/basic.toml
```

### Testing
```bash
cargo test
cargo test --doc
```

### Linting & Format
```bash
cargo fmt
cargo clippy -- -D warnings
```

---

## Key Concepts

- **Agentic Performance**: Autonomous test orchestration via AI (Gemini) for optimal chaos scenarios.
- **ARM-Optimized**: Extreme efficiency on Oracle Cloud ARM64 instances (4 vCPU × 24GB).
- **Calm UI**: High-contrast, dense-grid dashboard without JavaScript complexity (Leptos WASM).
- **ADRs**: Automated Architecture Decision Records generated post-test.
- **Embedded Stack**: NATS + SurrealDB bundled for zero external dependencies (except Gemini API).

---

## Phases (Roadmap)

1. **Phase 1**: Core load generation & basic stress testing (Rust daemon, CLI)
2. **Phase 2**: Chaos engineering library (network faults, latency injection)
3. **Phase 3**: Leptos dashboard + observability (OTLP ingest, live metrics)
4. **Phase 4**: Gemini integration (test planner, ADR generation)
5. **Phase 5**: Multi-region orchestration & self-healing workflows

---

## Workflow Rules

- ✅ **Always create a feature branch** before making changes (no direct commits to `main`)
- ✅ **Use taxonomy prefixes**: `feat/`, `fix/`, `docs/`, `chore/`, `refactor/`, `test/`, `perf/`, `ci/`, `build/`
- ✅ **Keep commits focused** — one responsibility per commit
- ✅ **Create pull requests** for all changes — user reviews before merge
- ✅ **All work appears under user's name** — no AI attribution in commits, PRs, or docs

---

## References

- [Rust Async](https://rust-lang.github.io/async-book/)
- [Leptos](https://leptos.dev/)
- [NATS.io](https://nats.io/)
- [SurrealDB](https://surrealdb.com/)
- [OpenTelemetry](https://opentelemetry.io/)
- [Gemini API](https://ai.google.dev/)
