title: Beerjs #41
author:
  name: Leonardo Gatica
  twitter: lgaticaq
  url: https://about.me/lgatica
  email: lgatica@protonmail.com
output: index.html
theme: juanbrujo/cleaver-beerjs
style: style.css
controls: true

--

<h1>Breakpoints en VSCode para Node y JavaScript</h1>

--

# ¿Por que usar breakpoints?

Los breakpoints nos permiten poder debugear el código de una forma mas dinámica y sencilla en vez de usar los `console.log()`.

--

# Debuggear Node (*pa los baken*)

--

## Modo manual

Habilitar el debuger

```bash
node --inspect index.js
```

Habilitar el debuger con un breakpoint inicial

```bash
node --inspect-brk index.js
```

La extencion de chrome [NIM (Node Inspector Manager)](https://chrome.google.com/webstore/detail/nodejs-v8-inspector-manag/gnhhdgbaldcilmgcpfddgdbkhjohddkj/) permite abrir automáticamente una pestaña con el debuger al usar --inspect

--

<img src="img/node-inspect.png">

--

# Debuggear JavaScript (*pa los fronen*)

--

## Plugin vscode-chrome-debug

```
ext install msjsdiag.debugger-for-chrome
```

<img src="https://github.com/Microsoft/vscode-chrome-debug/raw/master/images/demo.gif?raw=true">

--

## launch.json

```json
{
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Lanzar Chromium contra localhost (Linux)",
      "url": "http://localhost:3000",
      "webRoot": "${workspaceRoot}/src",
      "runtimeExecutable": "/usr/bin/chromium",
      "runtimeArgs": [
        "--remote-debugging-port=9222"
      ]
    },
    {
      "type": "chrome",
      "request": "launch",
      "name": "Lanzar Chrome contra localhost (Mac)",
      "url": "http://localhost:3000",
      "webRoot": "${workspaceRoot}/src",
      "runtimeArgs": [
        "--remote-debugging-port=9222"
      ]
    }
  ]
}

```
