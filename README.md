# Solmu: Autonomous Motor for Resilience and Chaos Engineering (Phases 1–5)

## 1. Product Vision

Develop **Solmu**, a single-binary tool focused on *Agentic Performance*. The objective is to unify Stress/Load Testing and Chaos Engineering in a single resilience pipeline, operated autonomously by AI, culminating in the generation of Architecture Decision Records (ADRs). The system must operate with extreme efficiency on ARM architectures (Oracle Cloud 4x24) and provide utility interfaces based on Calm UI principles.

---

## 2. Base Technology Stack

| Layer | Technology | Role in System |
|-------|-----------|---|
| **Backend/Daemon** | Rust (Axum, Tokio, Clap) | Load generation, network interception, CLI |
| **Frontend** | Leptos (SSR + WASM) | Reactive dashboard via Signals, no JS toolchains |
| **Messaging** | NATS (Embedded) | Event bus for chaos events and coordination |
| **Persistence** | SurrealDB (Embedded) | Log of chaos events, trace history |
| **Observability** | OpenTelemetry (OTLP) | Ingestion and analysis of performance degradation |
| **Intelligence** | Gemini API | Test planning (Architect) and post-mortem analysis |
| **Design System** | W3C Design Tokens | High-contrast interface optimized for dense grids |

---

## Quick Start

### Prerequisites
- Rust 1.70+
- Node.js 18+ (for frontend tooling)
- Cargo

### Installation
```bash
git clone https://github.com/renatobardi/solmu
cd solmu
cargo build --release
```

### Run the Daemon
```bash
./target/release/solmu daemon
```

### Open the Dashboard
Navigate to `http://localhost:3000` in your browser.

---

## Roadmap: Phases 1–5

### Phase 1: Core Load Generation
- ✅ Single-binary Rust daemon
- ✅ CLI for stress test configuration
- ✅ Basic HTTP/gRPC load injection

### Phase 2: Chaos Engineering Library
- Network fault injection (latency, packet loss, jitter)
- Service degradation simulation
- Automatic recovery scenarios

### Phase 3: Dashboard & Observability
- Leptos WASM dashboard (Signals-based reactivity)
- Live metrics via OpenTelemetry
- Historical event browsing (SurrealDB)

### Phase 4: AI-Driven Intelligence
- Gemini integration for test planning
- Autonomous ADR generation post-test
- Failure root-cause analysis

### Phase 5: Multi-Region Orchestration
- Distributed chaos across multiple clusters
- Self-healing workflow automation
- Cost optimization for ARM instances

---

## Architecture

See [CLAUDE.md](./CLAUDE.md) for the full technical overview, project structure, and development workflow.

---

## Contributing

1. Create a feature branch: `git checkout -b feat/your-feature`
2. Make focused commits
3. Push and open a pull request
4. Await review before merging to `main`

---

## License

See [LICENSE](./LICENSE) for details.

---

## Contact

For questions or contributions, visit the [GitHub repository](https://github.com/renatobardi/solmu).