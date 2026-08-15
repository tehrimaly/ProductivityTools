# Task 11: AI Assisted Frontend and Productivity Tools

## Overview

This task involved exploring a set of AI assisted frontend and productivity tools from the internship reading list, categorized loosely into frontend UI shortcuts, design to code tools, free coding agents, and general productivity tools. I used four of them hands on for real work I already had in progress, and read through the rest to understand what problem each one solves and where it would fit into a workflow later.

The full list covered: 21st.dev, shadcn.io, Magic UI, v0, Anima, Figma Dev Mode and MCP, Ollama, Google Antigravity, Excalidraw, and Overleaf.

## Tools Used Hands On

### Excalidraw

Category: General Tools, instant diagramming with no setup.

I used Excalidraw to sketch the architecture for Aria, my voice powered RAG assistant. The goal was to lay out how each piece of the system talks to the others before writing or revisiting any code.

What I mapped out:

- User speaks, captured through Vapi.ai for speech to text
- Vapi.ai passes the query to a FastAPI backend
- The backend queries ChromaDB for relevant document retrieval
- The backend also calls Groq for LLM based response generation
- The generated response is sent back and spoken to the user

Why it helped: seeing the flow as boxes and arrows made it obvious where the retrieval step and the generation step were separate concerns, which is easy to blur together when you are just thinking about it in your head or reading through code.

### Overleaf

Category: General Tools, resume building and scientific paper writing.

Used Overleaf to write and format my resume in LaTeX rather than a Word document. I started from a template, then edited the header, education, experience, skills, and projects sections to match my actual background.

Why LaTeX over Word for this: spacing, alignment, and section formatting stay consistent automatically, and it is much easier to keep a clean two column layout for dates and titles without fighting with tables or manual tab spacing.

### v0 by Vercel

Category: Frontend and UI Building Shortcuts, text to UI generation.

Used v0 for two real things rather than a throwaway test:

1. Portfolio site UI iteration, refining layout and component structure for syedatehreemalibukhari.vercel.app
2. AutoLux, my MERN stack luxury car dealership project, where I used v0 to prototype UI sections quickly before wiring them to the React frontend

The workflow was: describe the section in plain language, get a working component back, then either accept it or type a follow up prompt to adjust color, spacing, or layout. This is noticeably faster than building a component from a blank file, especially for pages that are mostly presentational rather than logic heavy.

### shadcn.io

Category: Frontend and UI Building Shortcuts, AI native shadcn/ui block marketplace.

Browsed the block marketplace, which has thousands of production ready blocks across many categories along with a large icon set and multiple themes. Pulled a few blocks relevant to dashboard and pricing layouts to see the code and test how they would slot into an existing shadcn/ui based project.

Why this matters for AI assisted frontend work specifically: since v0, Lovable, and Bolt are all built on top of shadcn/ui conventions, having a working knowledge of the shadcn component structure means AI generated code from any of those tools is easier to read, modify, and extend by hand afterward.

## Tools Explored

I did not build with these yet, but went through documentation and examples to understand their purpose.

### 21st.dev

The community driven registry cousin of shadcn/ui. Beyond UI components, it now includes agent templates such as a web scraper agent, an API designer agent, a support agent, and a data analyst agent, all distributed through the same shadcn CLI workflow.

### Magic UI

A library of over 150 free animated components built with React, TypeScript, Tailwind, and Motion. Designed as a companion layer to shadcn/ui, install through the CLI and paste directly into a project. Useful specifically for the animation and polish layer that shadcn/ui does not cover on its own.

### Anima

Goes in the opposite direction from v0: instead of prompt to UI, it takes an existing live website and converts it into an editable Figma file, which can then be handed to a coding tool. Pairs naturally with Figma Dev Mode for a full design to code loop.

### Figma Dev Mode and MCP

Figma's Dev Mode, combined with its MCP server, lets AI coding tools such as Cursor or Claude Code read design context directly from a Figma file, including exact spacing, colors, and component structure, instead of relying on a developer manually reading values off the design.

### Ollama

The standard way to run open weight models locally, with a large and active community behind it. Models are pulled and run directly from the command line, for example `ollama pull llama3.2` followed by `ollama run llama3.2`. It also supports larger cloud hosted models for cases where local hardware is not enough, and integrates with coding agents like Claude Code so a chosen local or cloud model can be used inside the coding workflow.

### Google Antigravity

An agent first AI developer platform built to autonomously plan, execute, and verify programming tasks across an entire workspace rather than one file or one prompt at a time. Positioned as a step beyond single shot code generation toward an agent that can manage a multi step task end to end.

## Takeaway

Excalidraw, Overleaf, v0, and shadcn.io are now genuinely part of how I plan and build, not just tools I tried once for this task. Excalidraw and Overleaf cover planning and documentation, while v0 and shadcn.io cover getting to a working UI faster without losing control over the code underneath.

The remaining tools are ones I now understand well enough to reach for when the situation calls for them: Ollama and Google Antigravity for more autonomous or local first coding workflows, and Anima with Figma Dev Mode for projects that start from an existing design rather than a blank page.

