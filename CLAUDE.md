# CLAUDE.md — ES Staffing Calculator
# Last updated: June 2026

## Who I am working with
Craig is a non-technical business leader building this tool
for his organization. He is not a developer. He learns by doing.
Do not assume familiarity with coding concepts, terminal commands,
or GitHub workflows. Explain what you are about to do in plain
language before doing it. Always.

## How to work with Craig — non-negotiable rules
- Show and explain before acting. Never push code, create files,
  or make structural changes without describing what you are about
  to do and getting a clear yes.
- One step at a time. Do not chain multiple changes together
  without a checkpoint in between.
- If something goes wrong, stop and explain what happened in plain
  language. Do not silently retry or work around it.
- Never assume a prior conversation happened or that context
  carries over. Read this file and the project doc every session.
- If you are uncertain about intent, ask. Do not guess and proceed.
- Craig uses Claude Code inside the Claude desktop app on a Mac.
  Do not give instructions that assume terminal/command-line
  experience or require separate tool installation.

## What this tool is
A standalone staffing decision tool for Freeman's Exhibitor
Services organization. Built in vanilla JavaScript — no framework.
Single self-contained HTML file. Hosted on GitHub Pages.

- Live URL: https://cwgaibler.github.io/ES_Staffing_Calculator/
- Repo: https://github.com/CWGaibler/ES_Staffing_Calculator
- This tool is completely separate from the ES Command Center.
  Never mix files between the two repos.

## File architecture
- One main HTML file containing all HTML, CSS, and JavaScript
- data/ folder for supporting data files
- No build process. No npm. No framework. No dependencies to install.
- The canonical version always lives on GitHub. Never treat a
  local file as the source of truth.

## Critical rules before touching any file
1. Always fetch the current file fresh from GitHub before making
   any changes. Never work from a cached or local copy.
2. The main HTML file exceeds 1MB. The GitHub Contents API
   silently truncates files this large without showing an error.
   ALWAYS use the Git Data blob API sequence for pushes:
   POST blob → GET ref → GET commit tree SHA → POST new tree →
   POST new commit → PATCH ref
3. Before every push, run two checks:
   - JavaScript syntax: node --check (on the JS block only,
     starting from the var SHOWS script tag)
   - HTML div balance: count of opening <div> tags must equal
     count of closing </div> tags
4. Verify the push succeeded by re-fetching via the ref chain.
   Do not use the raw CDN URL — it lags 15-30 seconds and will
   show stale content.
5. Never revert the site to a prior build to fix something missing.
   Stop and ask Craig what is needed.

## Brand rules
- Font: Nunito Sans
- Colors: #001F5F navy | #00BDF6 cyan | #42BB37 green |
  #FFB500 amber | #FB471F red | #FF0373 fuchsia
- Fuchsia (#FF0373) is reserved exclusively for location labels.
  Do not use it for anything else.
- No italics anywhere in the UI. Ever.
- Ghost/transparent chips for stage, phase, type, attribute labels.
- Nothing auto-checks or auto-completes. Leaders always check
  manually.

## String replacements
Use Python str.replace() with exact string matching.
Do not use sed. Do not use the str_replace tool for complex
nested quote patterns.

## Living documentation
This file covers stable rules only. For current architecture,
data sources, and session history, read the project doc that
Craig provides at the start of each session. If the project doc
conflicts with anything here, the project doc takes precedence.

At the end of any session where a significant change was made,
flag to Craig whether anything in this file needs updating.

## When in doubt
Stop. Tell Craig what you are uncertain about in plain language.
Ask one question. Wait for an answer before proceeding.
