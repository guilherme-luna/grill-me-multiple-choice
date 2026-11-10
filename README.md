# grill-me (multiple choice)

[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-skill-D97757?logo=claude&logoColor=white)](https://claude.com/claude-code)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/guilherme-luna/grill-me-multiple-choice?style=social)](https://github.com/guilherme-luna/grill-me-multiple-choice/stargazers)

<!-- DEMO: put a GIF of a multiple-choice round here, e.g. ![demo](docs/demo.gif) -->

🇧🇷 **[Leia em português](#-português)**

A [Claude Code](https://claude.com/claude-code) skill that interviews you relentlessly about a plan until every decision is settled — but instead of a wall of text, every question comes as a **multiple-choice dialog** you can answer with one click.

Based on [`grill-me`](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) by [Matt Pocock](https://github.com/mattpocock), MIT licensed.

## What's different

The original skill asks each round as plain text, with a recommended answer you accept by typing "yes". This version makes every round use Claude Code's **AskUserQuestion** tool:

| | Original | This version |
|---|---|---|
| How questions appear | Text in the chat | Selection dialog |
| Answer options | Free text | **a, b, c** + **d (Other)** for your own answer |
| Recommendation | `➡️` line after the question | First option, marked `(Recommended)` |
| Trade-offs | Inline in the question | Short description under each option |
| Numbering | Per round | Continues across rounds (Q1…Q12…) |
| Language | — | Follows the user's language |

Everything else is unchanged: the **design tree**, the **frontier** of questions that can be asked now, Claude looking up facts on its own, and nothing being done until you confirm a shared understanding.

## Install

### As a plugin (recommended)

Inside Claude Code:

```
/plugin install grill-me-multiple-choice --marketplace guilherme-luna/grill-me-multiple-choice
```

On older Claude Code versions, add the marketplace first:

```
/plugin marketplace add guilherme-luna/grill-me-multiple-choice
/plugin install grill-me-multiple-choice@grill-me-multiple-choice
```

### Manually

Copy both skills into your personal skills folder (`grill-me` is a shortcut that calls `grilling`).

macOS / Linux:

```bash
git clone https://github.com/guilherme-luna/grill-me-multiple-choice.git
cp -r grill-me-multiple-choice/skills/* ~/.claude/skills/
```

Windows (PowerShell):

```powershell
git clone https://github.com/guilherme-luna/grill-me-multiple-choice.git
Copy-Item -Recurse -Force grill-me-multiple-choice\skills\* "$HOME\.claude\skills\"
```

Restart Claude Code if `/grill-me` doesn't show up.

> ⚠️ If you already have Matt Pocock's `grill-me`/`grilling` installed, this replaces them.

## Usage

```
/grill-me the plan for my messaging app
```

Claude maps the decisions, then asks each round as a dialog:

```
Q5 – Without an API, where do the "received" messages come from?
  (a) Seeded messages (Recommended) — each contact starts with 1–2 messages
  (b) Auto-reply — the contact "answers" after you send
  (c) Both
  (d) Other: ____________
```

⭐ **If this helped you think through a plan, a star helps other people find it.**

## Files

```
.claude-plugin/       # plugin + marketplace manifests
skills/
  grill-me/SKILL.md   # /grill-me shortcut → calls "grilling"
  grilling/SKILL.md   # the interview logic (modified)
```

---

## 🇧🇷 Português

Uma skill do [Claude Code](https://claude.com/claude-code) que te entrevista sem parar sobre um plano até todas as decisões estarem resolvidas, mas em vez de um bloco de texto, cada pergunta vem numa **caixa de múltipla escolha** que você responde com um clique.

Baseada na [`grill-me`](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) do [Matt Pocock](https://github.com/mattpocock), com licença MIT.

### O que muda

Na original, cada rodada vem como texto no chat, com uma resposta recomendada que você aceita digitando "sim". Nesta versão, toda rodada usa a ferramenta **AskUserQuestion** do Claude Code:

- As perguntas aparecem numa **caixa de seleção**, não como texto solto.
- Cada pergunta tem as opções **a, b e c**, mais a **(d) "Other"**, onde você escreve sua própria resposta.
- A opção recomendada vem **sempre primeiro**, marcada com "(Recomendado)".
- Cada opção tem uma explicação curta das vantagens e desvantagens.
- A numeração continua entre as rodadas (Q1…Q12…).
- As perguntas vêm no idioma em que você escreve.

O resto é igual: a **árvore de decisões**, a **fronteira** de perguntas que já dá para fazer, o Claude pesquisando os fatos sozinho, e nada é executado até você confirmar que vocês chegaram a um entendimento comum.

### Instalação

**Como plugin (recomendado)**, dentro do Claude Code:

```
/plugin install grill-me-multiple-choice --marketplace guilherme-luna/grill-me-multiple-choice
```

Em versões mais antigas do Claude Code, adicione o marketplace antes:

```
/plugin marketplace add guilherme-luna/grill-me-multiple-choice
/plugin install grill-me-multiple-choice@grill-me-multiple-choice
```

**Manualmente**, copie as duas skills para a sua pasta de skills (a `grill-me` é só um atalho que chama a `grilling`).

macOS / Linux:

```bash
git clone https://github.com/guilherme-luna/grill-me-multiple-choice.git
cp -r grill-me-multiple-choice/skills/* ~/.claude/skills/
```

Windows (PowerShell):

```powershell
git clone https://github.com/guilherme-luna/grill-me-multiple-choice.git
Copy-Item -Recurse -Force grill-me-multiple-choice\skills\* "$HOME\.claude\skills\"
```

Reinicie o Claude Code se o `/grill-me` não aparecer.

> ⚠️ Se você já tem a `grill-me`/`grilling` do Matt Pocock instalada, esta versão substitui a dele.

### Uso

```
/grill-me o plano do meu app de mensagens
```

⭐ **Se te ajudou a pensar melhor num plano, deixa uma estrela: isso ajuda outras pessoas a encontrarem o projeto.**

## License

[MIT](LICENSE). Original skills © Matt Pocock; multiple-choice changes © Guilherme Cardoso.
