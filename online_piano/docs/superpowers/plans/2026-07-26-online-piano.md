# Online Piano Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a local single-page 88-key web piano that can be played with mouse, touch, and computer keyboard.

**Architecture:** A single static `index.html` contains HTML, CSS, and JavaScript. JavaScript generates the 88-key model, renders the keyboard, maps user input to notes, and uses the Web Audio API for synthesis.

**Tech Stack:** HTML, CSS, vanilla JavaScript, Web Audio API.

## Global Constraints

- No external dependencies.
- Create a static `index.html` that can be opened directly from disk.
- Render all 88 piano keys from A0 through C8.
- Support pointer, touch, and computer-keyboard performance.
- Include octave, sustain, volume, and active-note feedback controls.

---

### Task 1: Build the Single-Page Piano

**Files:**
- Create: `index.html`

**Interfaces:**
- Produces: Browser page with `createPianoKeys()`, `renderKeyboard()`, `playNote(note)`, `releaseNote(note)`, and keyboard event handlers.

- [ ] **Step 1: Create the document shell**

Add a complete HTML document with a top control bar, active note display, keyboard viewport, and template-free JavaScript entry point.

- [ ] **Step 2: Style the piano**

Add responsive CSS for the app layout, scrollable 88-key keyboard, white keys, black keys, pressed states, and compact controls.

- [ ] **Step 3: Generate and render 88 keys**

Implement `createPianoKeys()` to return A0 through C8 and `renderKeyboard()` to draw keys with correct black-key positioning.

- [ ] **Step 4: Add Web Audio synthesis**

Implement `playNote(note)` and `releaseNote(note)` with oscillator layers, gain envelopes, filtering, volume control, and sustain-aware release.

- [ ] **Step 5: Add pointer and keyboard controls**

Wire pointer down/up/cancel/leave events to every key. Map computer keys to the selected octave and prevent repeated keydown from retriggering held notes.

- [ ] **Step 6: Add final polish and verification hooks**

Show the active note, update octave and sustain controls, add accessible labels, and expose `window.__pianoTest` with key count and note names for quick console verification.

### Task 2: Verify the Page

**Files:**
- Read: `index.html`

**Interfaces:**
- Consumes: `window.__pianoTest.keyCount`, `window.__pianoTest.firstNote`, and `window.__pianoTest.lastNote`.

- [ ] **Step 1: Start a local static server**

Serve the folder locally so the page can be checked in a browser.

- [ ] **Step 2: Verify static expectations**

Confirm the page loads and reports exactly 88 keys, first note `A0`, and last note `C8`.

- [ ] **Step 3: Verify interaction expectations**

Confirm clicking a visible key sets the active note, and keyboard input triggers a mapped note without layout breakage.
