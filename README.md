# SYNKROOVE

**Turn sound into light. Build your own rave.**

Synkroove is an open-source DIY project exploring music-synchronized lighting for DJ sets, electronic music and home parties.

The goal is to build a modular system that transforms musical rhythm into programmable light effects, combining C++, desktop software and addressable LEDs.

From a virtual LED strip on your screen to custom-built LED tubes in your room, Synkroove aims to make creative DJ lighting more accessible, hackable and reproducible.

> 🚧 **Status: Early development.** The architecture and initial software prototype are being defined. Hardware control and DJ software integrations are future milestones.

## ✨ Vision

- 🎛️ **Beat-synchronized lighting** — create effects driven by BPM and rhythmic events.
- 🌈 **Programmable effects** — experiment with colors, palettes, transitions and patterns.
- 🖥️ **Desktop application** — control and preview lighting from Linux.
- 🧠 **C++ at the core** — build a modular, testable engine for timing and effects.
- 🔌 **DIY hardware** — plan support for addressable LED strips and, eventually, custom LED tubes.
- 🎚️ **DJ integration** — explore ways to receive tempo and beat information from DJ software.
- 🛠️ **Open and reproducible** — document the design so other people can experiment and build their own setups.

## 🧭 Development roadmap

### Phase 0 — Architecture
- [x] Define the initial project direction.
- [x] Establish a software-first development approach.
- [ ] Document the architecture and technical decisions.

### Phase 1 — Desktop foundation
- [ ] Set up the C++ and Qt development environment.
- [ ] Create the initial desktop application.
- [ ] Configure the build system with CMake.

### Phase 2 — Rhythm engine
- [ ] Implement a BPM-based beat clock.
- [ ] Support start, stop and tempo changes.
- [ ] Add automated timing tests.

### Phase 3 — Virtual lighting
- [ ] Render a virtual LED strip.
- [ ] Implement the first lighting effects and color palettes.
- [ ] Synchronize animations with rhythmic events.

### Phase 4 — External synchronization
- [ ] Evaluate MIDI and audio-based synchronization.
- [ ] Investigate DJ software integration options.
- [ ] Design a documented interface for external tempo sources.

### Phase 5 — Hardware
- [ ] Design a serial communication protocol.
- [ ] Explore ESP32-based LED control.
- [ ] Test addressable LED strips.
- [ ] Investigate modular LED tubes and multiple lighting zones.

*Roadmap items describe intended work, not currently available features.*

## 🏗️ Planned architecture

Synkroove is designed around separate modules:

- **Desktop application:** user interface, controls and visual preview.
- **Beat clock:** tempo, beat timing and rhythmic events.
- **Effect engine:** lighting patterns, palettes and transitions.
- **Output layer:** virtual rendering first, physical LED output later.
- **Integration adapters:** future connections to external music or DJ software.

The initial prototype will use a simulated BPM source. This allows development and testing without a DJ controller, LED strips or a microcontroller.

## 🧰 Planned technology stack

| Component | Initial direction |
|---|---|
| Language | Modern C++ |
| Desktop UI | Qt |
| Build system | CMake |
| Development platform | Linux |
| Future microcontroller | ESP32 |
| Future LED output | Addressable RGB LEDs |
| Communication | USB serial, subject to implementation |

Technology choices may evolve as the prototype develops.

## 🚀 Getting started

Synkroove is currently in the planning and early-development stage. Build instructions will be added once the initial application and project structure are available.

No physical hardware is required for the planned first software milestone.

## 🤝 Contributing

Ideas, discussions, bug reports and contributions will be welcome as the project becomes functional.

Potential areas for collaboration include:
- C++ architecture and testing.
- Lighting effects and visual design.
- MIDI and DJ software integration.
- LED hardware and power design.
- Linux support and documentation.

Please open an issue to discuss substantial changes before submitting a pull request.

## 🎯 Long-term goal

Build an accessible, modular and open-source lighting system that brings DJ sets to life — from a desktop simulation to DIY LED strips, tubes and room-scale installations.

**Synkroove — Sync your sound. Light your world.**

## 📄 License

A license has not yet been selected. A license will be added before the project begins accepting contributions under defined reuse terms.
