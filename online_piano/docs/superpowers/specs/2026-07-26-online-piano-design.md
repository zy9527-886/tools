# Online Piano Design

## Goal

Build a single-page web piano that opens locally and can be played online in a browser.

## Scope

- Create a static `index.html` experience with no external dependencies.
- Render all 88 piano keys from A0 through C8.
- Allow mouse, touch, and computer-keyboard performance.
- Generate sound in the browser with the Web Audio API.
- Include practical controls for octave selection, sustain, volume, and visible note feedback.

## Interface

The first screen is the piano itself. A compact top bar shows the title, active note, octave controls, sustain toggle, and volume slider. The keyboard fills the rest of the page horizontally and can scroll on narrow screens.

White and black keys use familiar piano proportions. Pressed keys visibly depress and glow so the player can understand what is sounding.

## Sound

Each note is synthesized with layered oscillators, a short attack, smooth decay, and filtered brightness to approximate a playable piano-like tone without samples. Notes release naturally, with longer release while sustain is enabled.

## Keyboard Mapping

Computer keys cover a playable range starting at the selected octave. The layout uses common music-app mappings:

- White notes: `A S D F G H J K L ;`
- Black notes: `W E T Y U O P`

Octave buttons shift the computer-keyboard range while the on-screen 88-key piano remains complete.

## Verification

The page should load from disk, show 88 keys, play notes on pointer and keyboard input, release notes correctly, and remain usable on desktop and mobile widths.
