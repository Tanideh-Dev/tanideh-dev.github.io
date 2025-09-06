# tanideh-dev.github.io

This repository hosts the **GitHub Pages root site** for [tanideh-dev](https://github.com/tanideh-dev).

It redirects visitors from:

👉 https://tanideh-dev.github.io  

to the main project page:

👉 https://tanideh-dev.github.io/Tanideh  

---
**Tanideh (تنیده)** is a decentralized, transparent, bot-resistant voting application.  
Learn more at the [Tanideh Project Website](https://tanideh-dev.github.io/Tanideh).


------------------------------------------------------------------

```mermaid
flowchart TB
  %% Tanideh – Vote Dissemination Circle (subset of 99 clients)

  %% === Client ring (circle layout) ===
  C1((C1)) --- C2((C2))
  C2 --- C3((C3))
  C3 --- C4((C4))
  C4 --- C5((C5))
  C5 --- C6((C6))
  C6 --- Cx((...))
  Cx --- C1

  %% === Vote dissemination subset ===
  C1 -. "subset of peers" .-> C2
  C1 -. "subset of peers" .-> C3
  C1 -. "subset of peers" .-> C4

  %% === Validation (EdDSA ed448) ===
  V["Validation: EdDSA (ed448)"]
  C2 -->|"vote + signature"| V
  C3 -->|"vote + signature"| V
  C4 -->|"vote + signature"| V

  %% === Gossip dissemination ===
  G["Gossip Engine: Controlled Epidemic"]
  V -->|"valid"| G

  %% === Damping ===
  D["Damping Coefficient (prevents flooding)"]
  G -->|"echo"| D
  D -. "throttles" .- G

  %% Echo back into ring
  D -. "echo (damped)" .-> C5
  D -. "echo (damped)" .-> C6
  D -. "echo (damped)" .-> Cx

  %% === Styling ===
  classDef client fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef process fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef engine fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef control fill:#fff,stroke:#000,stroke-width:1px,color:#000;

  class C1,C2,C3,C4,C5,C6,Cx client
  class V process
  class G engine
  class D control

