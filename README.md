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

\begin{tikzpicture}[node distance=2cm, auto]
\tikzstyle{block} = [rectangle, draw, fill=blue!20, text centered, rounded corners, minimum height=1.5em]
\tikzstyle{line} = [draw, -latex']

\node [block] (cast) {Vote Cast};
\node [block, below of=cast] (validate) {Validation (Signature, Timestamp, Uniqueness)};
\node [block, below of=validate] (echo) {Echo (Controlled Gossip)};
\node [block, below of=echo] (expire) {Expiration / Renewal};

\path [line] (cast) -- (validate);
\path [line] (validate) -- (echo);
\path [line] (echo) -- (expire);
\end{tikzpicture}



