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
flowchart LR
  %% Tanideh – Vote Dissemination in a Fully Connected Mesh (K99)

  subgraph M["Client Mesh - Complete Graph (K99)"]
    direction LR
    C1((C1))
    C2((C2))
    C3((C3))
    C4((C4))
    C5((C5))
    Cx((... more))
    C1 --- C2
    C1 --- C3
    C1 --- C4
    C1 --- C5
    C2 --- C3
    C2 --- C4
    C2 --- C5
    C3 --- C4
    C3 --- C5
    C4 --- C5
  end

  C1 -. "subset of peers" .-> C2
  C1 -. "subset of peers" .-> C3
  C1 -. "subset of peers" .-> C4

  V["Local Validation: EdDSA (ed448)"]
  C2 -->|"vote + signature"| V
  C3 -->|"vote + signature"| V
  C4 -->|"vote + signature"| V

  G["Gossip Engine: Controlled Epidemic"]
  V -->|"valid"| G

  D["Damping Coefficient - prevents duplication & flooding"]
  G -->|"echo"| D
  D -. "throttles" .- G

  D -. "echo (damped)" .-> C5
  D -. "echo (damped)" .-> Cx

  %% === Styling for white background with dark text/lines ===
  classDef client fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef process fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef engine fill:#fff,stroke:#000,stroke-width:1px,color:#000;
  classDef control fill:#fff,stroke:#000,stroke-width:1px,color:#000;

  class C1,C2,C3,C4,C5,Cx client
  class V process
  class G engine
  class D control


