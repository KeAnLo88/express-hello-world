# Cyclic - Express Hello World

This is a basic starter Expressjs app with:

- Static file hosting
- Logging Middleware
- Catch-all handler that echoes request info

## Local Quick Start

- Clone to your local
- Install dependencies `npm install`
- Run locally `npm serve`
- Make requests
  - Browser: `http://localhost:3000/some/path?q=query+one&q=second+query&single=value`
  - Command line: `curl -i -XGET "http://localhost:3000/cmd/line-curl"`

## Deploy in under 10 seconds

[![Deploy to Cyclic](https://deploy.cyclic.app/button.svg)](https://deploy.cyclic.app/)
- Sets up instant continuous deployment on `git push`
- Realtime backend logs and API request monitoring

### Cyclic Runtime

- Cyclic hosts your app on serverless infrastructure. That means there is no guarantee of memory or file system persistence between requests.
- The runtime expects a nodejs entry point defined as:
  - package.json "main" field defines the entry point file (if missing uses index.js)
  - Entry point starts a server on `process.env.PORT`

## Say Hi

Ask a question or give us a shout out:

- 💌 hello@cyclic.sh
- 🐣 https://twitter.com/cyclicsoftware

\documentclass{article}
\usepackage{tikz}
\usetikzlibrary{shapes,arrows}

\begin{document}

\begin{tikzpicture}[node distance=2cm,auto]
  \node[draw,rectangle] (start) {Start};
  \node[draw,rectangle] (create) [below of=start] {Create Group};
  \node[draw,diamond] (decision) [below of=create] {Is the group public?};
  \node[draw,rectangle] (addpublic) [below left of=decision] {Add Members};
  \node[draw,rectangle] (savepublic) [below of=addpublic] {Save Group};
  \node[draw,rectangle] (addprivate) [below right of=decision] {Set Group Privacy};
  \node[draw,rectangle] (addmembers) [below of=addprivate] {Add Members};
  \node[draw,rectangle] (saveprivate) [below of=addmembers] {Save Group};
  \node[draw,rectangle] (end) [below of=saveprivate] {End};

  \path [->] (start) -- (create);
  \path [->] (create) -- (decision);
  \path [->] (decision) -| node[pos=0.3,above] {Yes} (addpublic);
  \path [->] (decision) -| node[pos=0.3,above] {No} (addprivate);
  \path [->] (addpublic) -- (savepublic);
  \path [->] (savepublic) -- (end);
  \path [->] (addprivate) -- (addmembers);
  \path [->] (addmembers) -- (saveprivate);
  \path [->] (saveprivate) -- (end);

\end{tikzpicture}

\end{document}

