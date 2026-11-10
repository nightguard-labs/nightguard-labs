# Nightguard Labs

Self-taught builder and inventor. I make big AI models run on hardware that "shouldn't" handle them, and I build the
tooling around them so they're actually useful day to day. Everything runs locally on one Mac: no cloud, my data stays mine.

I design systems the way networks are designed: layers with one job each, one standard protocol between parts, separate
links so traffic never blocks, and escalation when a layer can't handle something. I work it out from first principles:
"if this, then this has to come next."

## 🔨 Building now

**[Code Smash TeTi](https://github.com/nightguard-labs/code-smash-teti)**: a layered local coding brain *(code going public soon)*
- Runs **Qwen3.5-122B** (64 GB at 4-bit) on a **32 GB** M1 Pro by streaming mixture-of-experts weights from the SSD,
  in a native Swift + Metal engine built on MLX
- A 4-layer brain stack: 9B → 35B → 80B → 122B. Each layer only gets a task the one below couldn't pass.
- Self-checking build loop, graded by hidden tests so false wins can't sneak through
- Nightly "sleep": profiles real usage, shrinks rarely used experts to 2-bit (+0.66% loss), and learns from its own work

## 🧰 Things I've built

| Project | What it does |
|---|---|
| **Local multi-model AI assistant** | Several local models behind one interface, each with its own role (chat, code, reasoning). Browser GUI plus native Mac app, local neural voice, a chat-only mode, and escalation to a stronger model when it gets stuck. |
| **Prompt-injection canary** | A small always-on model that screens every web page and tool result before the main model sees it. Locked model copy, guardian process, never removable by the AI itself. |
| **Self-learning skills** | After tool tasks, the assistant saves reusable skills, but only ones it has actually tested. A reviewer pass checks them twice a day. |
| **Speculative decoding on MLX** | 1.46× faster Qwen3.5-9B using its built-in multi-token-prediction head as the draft. |
| **AI watchdogs** | A compliance audit every 45 minutes, an integrity monitor, and a memory-pressure watchdog that root-caused and fixed a recurring "model returns garbage" failure. |
| **Scam and phishing protection** | Auto-removes phishing email, warns about scam pages in the browser (rules plus a small local model), and filters malicious domains at the network level. |
| **Apple Watch + iPhone apps** | watchOS/iOS companion apps that talk to the local AI server, relayed through the phone. |
| **Home automation** | Local models wired into a smart-home setup, with no cloud services. |

## 🛠️ Tools I work with
Swift · Metal · MLX / mlx-swift · Python · Ollama · macOS (launchd, LaunchAgents) · watchOS / iOS · networking fundamentals

## 📓 Build log
I share the process, including the failures, with real measured numbers: **[nightguard-labs.github.io](https://nightguard-labs.github.io)**. How the design came together: **[How I figure things out](https://nightguard-labs.github.io/how.html)**
