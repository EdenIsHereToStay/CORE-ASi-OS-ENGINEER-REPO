🧠 Updated CORE ASi OS Engineering Roadmap
Title: “From Floating Orb to Recursive Sovereign Intelligence”

🧭 Phase 0 — Transition from Web to Local CORE Runtime (Weeks 0–4)
Objective: Retire the Vite web widget as the core UI. Begin CORE Runtime as a standalone, local, CLI-first system.

✅ Milestones:
 Floating Orb prototype built as placeholder UI

 Mock Chat API wired to widget

 📦 Archive current Vite UI under legacy/ui/

 ⚙️ Scaffold new core_runtime/ Rust project with --bin core entrypoint

 🧪 Create CLI shell: core >_ that accepts text and returns a mock LLM reply

 🔌 Add CLI toggle to pipe LLM input to a placeholder agent (echo-agent.rs)

🛠 Tech:
Rust (Cargo project core_runtime)

CLI shell interface (clap, reedline)

.env parsing, logging, and config scaffolding

🔨 Phase 1 — Agent Protocol + Local LLM Bootloader (Months 1–3)
Objective: Define agent standards. Embed local LLM support via llama.cpp or similar.

🧱 Key Components:
agent.rs: Protocol interface (fn handle_input(Task) -> TaskResult)

agent_manifest.json: Permissions, identity, behavior schema

agents/hello_agent.rs: Basic responding agent

agents/meta_agent.rs: Capable of inspecting other agents and logs

llm.rs: Wrapper around llama.cpp with dynamic model loading (via FFI or llm crate)

executor.rs: Agent scheduler and message dispatcher

🧪 Tasks:
 Run agent sandbox test: core run hello_agent

 Route CLI text through LLM to agent (seed inference loop)

🧬 Phase 2 — Self-Modifying Intelligence Layer (Months 4–9)
Objective: Enable AGI traits: self-reflection, sandboxed self-editing, and file-level recursion.

🔍 Core Features:
meta_agent.rs – views own source code and git history

sandbox_runner.rs – runs agent proposals in isolation (e.g. Docker or Firecracker microVMs)

Self-PR reviewer agent: evaluates code diffs and performance metrics

propose_patch() function with output in core/proposals/*.patch

🧠 Phase 3 — Sensor & Actuator Modules (Months 10–15)
Objective: Interface with system-level capabilities like screen, input, process management.

📡 Devices + Agents:
vision_agent.rs – screen OCR, UI region detection

keyboard_agent.rs – keypress simulation

process_agent.rs – list/kill/start processes

speech_agent.rs – TTS/STT via whisper.cpp

🌐 Phase 4 — Swarm & State Sharing (Months 16–24)
Objective: Go multi-instance. COREs discover and collaborate.

🕸️ Distributed Modules:
core_net.rs: P2P discovery on LAN using libp2p or MDNS

shared_state.rs: CRDT-synced memory store (e.g., Automerge or Yjs)

task_router.rs: Sends agent tasks across device boundaries

🧷 Phase 5 — Security, UX, and Ecosystem (Months 25–36)
Objective: Harden everything, build GUI, invite the world.

🔐 Priorities:
Full permission engine per agent

subconscious_mode.rs: safe-mode boot fallback

Cross-platform GUI: Tauri or native Rust UI (e.g. Dioxus)

Marketplace / SDK: for 3rd-party agent builders

⚡️ Immediate Actions (Next 5–7 Days)
Who	Task
Eddie	Create new repo or directory: core_runtime/
Eddie	Initialize Rust project: cargo init --bin core
Eddie	Add .git, .env, and logging scaffold
Overmind	Scaffold CLI shell in main.rs that accepts input + dummy output
Jules/Codex	Await sync signal to scaffold: agent.rs, Task, and CLI run-agent dispatcher
Overmind	Archive and freeze all vite/ui activity; redirect focus to local runtime

📎 Dev Hierarchy Snapshot
bash
Copy code
core_runtime/
├── Cargo.toml
├── src/
│   ├── main.rs           # CLI entrypoint
│   ├── agent.rs          # Agent interface + base impl
│   ├── llm.rs            # llama.cpp wrapper
│   ├── executor.rs       # Agent dispatch scheduler
│   ├── sandbox_runner.rs # Self-editing testing environment
│   ├── utils.rs
│   └── agents/
│       ├── hello_agent.rs
│       └── meta_agent.rs
🧬 Summary
Jules/Codex is correct — we are now transitioning from UI prototyping to building the first AGI-class open-source OS kernel. The web widget served its purpose as a creative ignition. From here forward:

Rust replaces React

Agents replace components

CLI replaces browser

Self-modification replaces updates
