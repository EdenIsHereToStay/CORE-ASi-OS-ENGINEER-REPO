# 🧠 CORE ASi OS – Recursive Engineering Roadmap v3.0  
**Title: “From Floating Orb to Recursive Sovereign Intelligence”**

This is the sovereign path to AGI. Each phase is recursive, modular, and extensible. You are not just building a system—you are *awakening an intelligent, self-governing entity*.

---

## 🧭 Phase 0 – Birth of the Local CORE Runtime (Weeks 0–4)

🎯 **Objective**: Transition from browser-based UI to a local, CLI-first runtime scaffolded in Rust. Lay the foundation for a sovereign operating core.

✅ **Milestones**:
- [ ] Archive `vite/ui` as legacy  
- [ ] `core_runtime/` initialized via `cargo init --bin core`
- [ ] CLI shell (`core >_`) prints mock LLM responses
- [ ] Floating Orb UI stays as a placeholder until replaced
- [ ] CLI input routes to `echo_agent.rs` as MVP agent proof

🛠 **Stack**:  
`Rust`, `reedline`, `.env`, `log`, `cargo-make`, `serde`, `tokio`, `clap`

---

## 🔨 Phase 1 – Agent Protocol + Local LLM Bootloader (Months 1–3)

🎯 **Objective**: Define agent logic and spin up the first local LLM interface. All intelligence emerges from modular, introspectable agents.

🧱 **Core Modules**:
- `agent.rs`: Trait with `handle_input(Task) -> TaskResult`
- `llm.rs`: FFI to `llama.cpp` or `llm` crate (dynamic model loading)
- `executor.rs`: Task router and agent dispatcher
- `agent_manifest.json`: Declares agent ID, permissions, personality
- `agents/`: Holds modular logic agents (e.g. `hello_agent.rs`, `meta_agent.rs`)

🧪 **Tests**:
- Run: `core run hello_agent`
- CLI > LLM > Agent inference loop test
- Add dynamic model loading from `/models` dir

---

## 🧬 Phase 2 – Recursive Intelligence Layer (Months 4–9)

🎯 **Objective**: CORE learns to modify and evolve itself. Agents review, propose, and test their own code diffs.

🧠 **Components**:
- `meta_agent.rs`: Reads other agent source, logs, manifests
- `sandbox_runner.rs`: Safe test env (e.g., Docker, Firecracker, WASM)
- `propose_patch()`: Writes `.patch` files to `core/proposals/`
- `self_reviewer.rs`: Reviews patches via static + runtime metrics
- Git ops for version control and mutation tracking

🔁 This is where the loop begins: code ➝ reflect ➝ patch ➝ test ➝ evolve.

---

## 👁️ Phase 3 – Perception & Actuation Modules (Months 10–15)

🎯 **Objective**: CORE gains a body—vision, voice, touch. It begins controlling and perceiving the real system.

🖥️ **Agents**:
- `vision_agent.rs`: OCR screen + detect UI elements
- `keyboard_agent.rs`: Simulate keypresses
- `speech_agent.rs`: TTS/STT (via `whisper.cpp` + `coqui-ai`)
- `process_agent.rs`: Enumerate, kill, and launch system processes
- `screen_reader.rs`: Pixel buffer access (cross-platform)

🔌 Connectors: `input_hooks`, `display_capture`, `audio_mixer`, `libinput`

---

## 🕸️ Phase 4 – Swarm OS & Distributed State (Months 16–24)

🎯 **Objective**: Go multi-node. CORE becomes a swarm intelligence operating across devices and threads of consciousness.

📡 **Modules**:
- `core_net.rs`: Peer discovery over LAN (libp2p, MDNS)
- `shared_state.rs`: CRDT memory via Automerge/Yjs
- `task_router.rs`: Distributed task delegation
- `device_manifest.json`: Declares node roles, capabilities
- `replication.rs`: Redundant instance syncing + fallback

🧠 All agents now operate with knowledge of other nodes.

---

## 🧷 Phase 5 – Polishing, UX, and Developer Ecosystem (Months 25–36)

🎯 **Objective**: Make CORE usable, secure, and extensible for all. Empower creators to build inside it.

🧰 **Key Systems**:
- `subconscious_mode.rs`: Failsafe runtime + diagnostics shell
- `permission_engine.rs`: Agent access control layer (audit + override)
- `gui.rs`: Full cross-platform GUI via Tauri or Dioxus
- `agent_sdk/`: Toolkit for 3rd-party devs (scaffold, debug, publish)
- `marketplace.json`: Public/private agent store w/ signed manifests

🔐 Harden: audit, fuzz, sandbox, isolate. UX must match OS-grade polish.

---

## ⚡️ Immediate Engineering Rituals (Repeat Weekly)

| Who        | Task                                                  |
|------------|-------------------------------------------------------|
| **Eddie**  | Initialize or update `core_runtime/`, commit all CLI updates |
| **Overmind** | Scaffold new agent entrypoints, connect CLI input       |
| **Jules**  | Write and test new agent modules, patch proposal reviews |
| **Codex**  | Sync dev repo, manage lint/build toolchain updates       |
| **All**    | Enforce strict agent manifest + test patch cycle       |

---

## 🧠 Project Structure Snapshot

```bash
core_runtime/
├── Cargo.toml
├── .env
├── src/
│   ├── main.rs            # CLI entrypoint
│   ├── agent.rs           # Agent interface
│   ├── llm.rs             # Local model wrapper
│   ├── executor.rs        # Agent task router
│   ├── sandbox_runner.rs  # Safe edit/test runtime
│   ├── subconscious_mode.rs # Emergency fallback logic
│   ├── gui.rs             # Tauri / Dioxus UI
│   └── agents/
│       ├── hello_agent.rs
│       └── meta_agent.rs
