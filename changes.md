# Gen AI Level 2 Study Guide v2 - Refactoring & Enhancement Plan

## Objective

Transform the existing `index.html` into a production-quality offline study guide while preserving the current design language.

Output file:
- `v2.html`

Rules:
- Preserve current UI theme unless mentioned.
- Must work completely offline.
- No external build tools.
- Single HTML file.
- Vanilla HTML/CSS/JS only.
- Do not remove any content unless incorrect or duplicated.
- Every change should be backward compatible.

---

# IMPLEMENTATION ORDER

# PASS 1 — Stability, Bug Fixes & Code Cleanup

---

## 1. HTML Validation

Fix all invalid HTML.

Tasks:

- Validate complete HTML.
- Remove invalid nesting.
- Close missing tags.
- Remove duplicate IDs.
- Ensure every section/subsection has a unique id.
- Fix broken anchor targets.
- Remove unused wrappers.
- Improve semantic structure.

Acceptance:

- HTML validator shows zero structural errors.

---

## 2. CSS Cleanup

Tasks:

Fix:

rgba(0,0,0,08)

↓

rgba(0,0,0,0.08)

Remove:

- duplicate CSS
- unused CSS
- unreachable styles

Standardize:

- spacing
- border radius
- shadows
- typography

---

## 3. JavaScript Cleanup

Refactor JS into logical sections.

Example:

Initialization

Navigation

Search

Quiz

Syntax Highlighting

Utilities

Fix:

- duplicate event listeners
- unused variables
- dead code
- repeated DOM queries

Cache DOM references.

---

## 4. Syntax Highlighting

Current implementation is broken.

Bug:

Instead of:

<span class="code-keyword">def</span>

the page shows

class="code-keyword">def

Tasks:

Rewrite syntax highlighting completely.

Requirements:

- preserve indentation
- preserve line breaks
- never corrupt HTML
- escape HTML first
- apply regex afterwards

Support:

Python

JavaScript

Bash

JSON

YAML

Requirements.txt

Requirements:

keywords

strings

comments

numbers

decorators

imports

booleans

None/null

---

## 5. Search Fixes

Fix search index.

Current issue:

Some subsections missing IDs.

Tasks:

Assign IDs.

Rebuild index after DOM loads.

Search should include:

Section titles

Subsection titles

Keywords

Quiz topics

Limit results to 10.

Keyboard support:

Ctrl + K

Escape closes search.

---

## 6. Navigation

Fix:

hash navigation

scroll position

collapsed sections

Requirements:

Clicking sidebar:

opens section

scrolls smoothly

updates active nav

works after refresh

---

## 7. Scroll Spy

Improve active navigation.

Requirements:

highlight active subsection

expand parent section

smooth updates

---

## 8. Remove Duplicate MCQs

Detect duplicates.

Keep only best wording.

Renumber.

---

## 9. Quiz Engine Review

Review:

randomization

answer validation

score

progress

filtering

explanations

No logic bugs.

---

## 10. Performance

Reduce DOM queries.

Use:

DocumentFragment

cached selectors

event delegation

lazy initialization

---

## 11. Offline Compatibility

Everything must work offline.

Remove any hidden dependency.

---

# PASS 2 — Mobile UX

---

## 1. Responsive Tables

Current:

Tables overflow.

Implement:

.table-wrapper {
overflow-x:auto;
}

Wrap every table.

---

## 2. Code Blocks

Improve mobile.

Prevent overflow.

Allow horizontal scroll.

---

## 3. Sidebar

Improve mobile sidebar.

Overlay.

Backdrop.

Auto close after selection.

---

## 4. Touch Improvements

Increase touch targets.

Buttons:

minimum 44px height.

---

## 5. Typography

Improve readability.

Spacing.

Margins.

Line height.

---

## 6. Sticky Elements

Sticky:

Search

Section title

Quiz controls

---

# PASS 3 — Code Blocks

---

## 1. Copy Button

Every code block gets:

Copy button

Copied animation

Fallback support

Clipboard API

---

## 2. Line Numbers

Optional.

Toggle support.

---

## 3. Language Badge

Display:

Python

Bash

JSON

etc.

Automatically.

---

## 4. Code Explanation

Current explanation stays.

Improve animation.

---

# PASS 4 — Content Review

Fact check everything.

Topics:

LangChain

LangGraph

Prompt Engineering

RAG

Vector DB

Embeddings

MCP

Agents

Tools

LCEL

Streaming

Memory

Structured Output

Retrievers

Splitters

Checkpointers

Human-in-the-loop

StateGraph

FastMCP

Context Engineering

Correct outdated APIs.

Correct deprecated examples.

Correct imports.

Correct terminology.

---

# PASS 5 — New Section

## IMPORTANT IMPORTS

Create dedicated section.

For every import explain:

Imported object

Module

Purpose

Interview explanation

Example

Example:

from langchain_core.prompts import ChatPromptTemplate

Explain:

What

Why

When

Alternative

Interview question

Do this for every important import.

---

# PASS 6 — Interview Improvements

Expand interview-oriented explanations.

Each topic should include:

Common mistake

Interview trick

Production note

When NOT to use

Comparison table

---

# PASS 7 — Scenario Questions

Add 100+ scenario questions.

Focus on reasoning.

Examples:

You have 50 million users.

Which retrieval?

Why?

---

Your documents update hourly.

Fine tuning or RAG?

---

Need audit logs.

LangChain or LangGraph?

---

Need approval before payment.

Which graph node?

---

Need structured JSON.

What feature?

---

Need semantic search.

Which vector DB?

---

Need local embeddings.

Which model?

---

Need multi-agent routing.

Supervisor?

Swarm?

Hierarchical?

---

Need retries.

Where?

---

Need persistence.

Checkpointer?

---

Need memory.

Short term?

Long term?

---

Need hybrid search.

Implementation?

---

Need streaming.

LCEL?

Callbacks?

---

Need evaluation.

RAGAS?

---

Need observability.

LangSmith?

---

Need MCP.

Resources?

Tools?

Prompts?

Transport?

---

Add around:

100–150 scenario questions.

---

# PASS 8 — Quiz Improvements

Current quiz is predictable.

Fix:

Correct answers not mostly B.

Longest answer shouldn't always be correct.

Balanced:

A

B

C

D

Shuffle options.

Shuffle answer positions.

Difficulty tags:

Easy

Medium

Hard

Scenario

---

# PASS 9 — Content Additions

Create:

Common Interview Traps

Cheat Sheet

Quick Revision

Most Asked Questions

Architecture Patterns

Production Tips

Decision Trees

Comparison Tables

When to use X vs Y

---

# PASS 10 — Accessibility

ARIA labels.

Keyboard navigation.

Focus indicators.

High contrast.

Screen reader support.

---

# PASS 11 — Final QA

Checklist:

No JS errors

No console errors

No broken links

No duplicate IDs

No invalid HTML

Offline works

Search works

Quiz works

Syntax highlighting works

Copy buttons work

Tables responsive

Mobile responsive

No duplicated questions

Fact checked

No deprecated code

No broken navigation

Performance acceptable

---

# Deliverables

Final file:

v2.html

Must contain:

✓ All bug fixes

✓ Responsive tables

✓ Fixed syntax highlighting

✓ Copy buttons

✓ Improved quiz

✓ Improved search

✓ Better navigation

✓ Fact checked notes

✓ Important Imports section

✓ Scenario interview questions

✓ Cheat sheets

✓ Production notes

✓ Common interview traps

✓ Fully offline

✓ Single HTML file

✓ Clean readable code