# PRIMM NeoPixel Loop Tutor
### An interactive, research-based CircuitPython loop tutor powered by a live NeoPixel strip simulation

**Built for:** Grades 11–12 Introduction to Programming with Python  
**Aligned to:** Georgia Standards of Excellence (GSE) for Computer Science 9–12  
**Developer:** Charles R. Drew Charter Senior Academy — Engineering & Technology Department

---

## What is this?

PRIMM NeoPixel Loop Tutor is a mobile-friendly, browser-based interactive learning app that teaches loop concepts in CircuitPython using a simulated 12-pixel NeoPixel LED strip as the primary teaching tool. Rather than presenting loops as abstract programming constructs, every concept is grounded in a visual, tangible outcome — lighting pixels, building patterns, and animating color sequences on a strip students can see respond in real time.

The app follows the **PRIMM pedagogical framework** — a research-based approach developed at King's College London — which builds comprehension progressively before asking students to produce code independently. When a student gets something wrong, the app never leaves them stuck: it explains the error, highlights the correct answer, and offers a similar example they must answer correctly before moving forward.

---

## What is a NeoPixel?

A NeoPixel is an individually addressable RGB LED — each pixel in a strip can be set to any color by sending it three values (red, green, blue) ranging from 0 to 255. NeoPixels are controlled in CircuitPython using the `neopixel` library and are a staple of physical computing, wearable electronics, and maker projects. This app simulates a 12-pixel NeoPixel strip so students can learn the programming concepts before ever touching hardware.

---

## The PRIMM Framework

| Phase | What the student does |
|---|---|
| **Predict** | Reads a CircuitPython code snippet and predicts what the NeoPixel strip will look like before running it |
| **Run** | Steps through the code in a simulated CircuitPython shell and watches the strip animate in real time |
| **Investigate** | Answers targeted questions to understand how and why the loop produces that pattern |
| **Modify** | Selects the correct modification to existing code to produce a new light pattern |
| **Make** | Chooses the correct original code solution from options — constructing a program from scratch |

> The full PRIMM sequence runs on the **first problem** of each concept. Subsequent problems enter mid-framework (at Modify), since the student has already been introduced to the concept and the strip provides ongoing visual reinforcement.

---

## The Live NeoPixel Strip

The 12-pixel strip sits at the top of every screen and is always visible. It behaves differently across phases:

- **Predict phase** — strip is off, waiting for the student's prediction
- **Run phase** — strip animates in real time as each line of code executes, with pixels lighting up one at a time as the loop iterates
- **Investigate / Modify / Make phases** — strip holds the final state from the Run phase as a persistent visual reference

Each pixel renders its actual RGB color with a soft glow effect. Index numbers (0–11) appear below each pixel so students can connect the code (`pixels[i]`) to a specific physical position on the strip.

---

## When a Student Gets Something Wrong

Getting an answer wrong does not stop progress. The app:

1. Highlights the **correct answer in green** so the student can see it immediately
2. Shows a **targeted explanation** of exactly why their choice was incorrect
3. Presents a **Similar Example** — a structurally identical problem with different pixel counts, colors, or ranges — that the student must answer correctly to move forward

This ensures students never advance past a concept they have not demonstrated understanding of, while avoiding dead ends that stall learning.

---

## Features

- **Animated NeoPixel strip** — pixels light up in real time as the CircuitPython shell executes, with color-accurate RGB rendering and a glow effect for lit pixels
- **CircuitPython shell** — the Run phase simulates stepping through code line by line, with execution commentary explaining what each line does to the strip
- **Real CircuitPython syntax** — all code uses the actual `neopixel` library syntax students would use on a physical Circuit Playground Express or Feather board
- **Similar examples** — wrong answers trigger a parallel problem on the same concept, keeping students in productive struggle rather than stuck or skipping ahead
- **Badge system** — students earn a named badge upon mastering each concept, providing visible recognition of progress
- **Mobile-friendly** — designed for phone screens first, works on any device without installation or login
- **Progress bar** — tracks advancement through all concepts and problems

---

## Curriculum Coverage — Unit 6: Loops in CircuitPython

**Concept 1 — for loops with range()**

Students learn to control exactly which pixels light up using a loop counter. Problems progress from lighting the first N pixels, to using `range(start, stop)` to target specific sections of the strip, to building patterns like progress bars and alternating pixel effects using the modulo operator.

**Concept 2 — while loops**

Students learn condition-based iteration using the NeoPixel strip as the feedback mechanism. Problems cover lighting pixels with a while loop, understanding what happens when `i += 1` is forgotten (infinite loop), counting down from pixel 11 to 0 using `i -= 1`, and the critical difference between `i < n` and `i <= n`.

**Concept 3 — nested loops**

Students learn to layer loops to create multi-frame color sequences. Problems cover cycling through a color list with nested for loops, calculating total iterations (outer × inner), building a theater chase effect using `range(offset, 12, step)`, and understanding why clearing the strip between frames is essential.

---

## Georgia Standards of Excellence Alignment

| Standard | Description |
|---|---|
| CS10-AP-4 | Implement algorithms using selection and iteration to solve problems |
| CS10-AP-5 | Trace and evaluate programs that use conditionals and loops to determine output |
| CS10-AP-8 | Use lists and iteration to store, access, and manipulate collections of data |
| CS10-AP-3 | Develop programs that clearly communicate results to users |
| CS10-IC-1 | Evaluate the ways computing innovations impact personal, ethical, and social practices |

---

## Connection to Physical Computing

This app is designed as a bridge between screen-based programming and physical hardware. Every code example in the app can be copied directly onto a Circuit Playground Express, Feather M0, or any other CircuitPython-compatible board with a NeoPixel strip attached to pin D6. Students who complete this app have working CircuitPython loop programs ready to flash to real hardware.

Suggested hardware pairing:
- **Adafruit Circuit Playground Express** — built-in 10 NeoPixels, no wiring required
- **Adafruit Feather M0 or M4** — paired with a 12-pixel NeoPixel strip on pin D6
- **Adafruit NeoPixel Jewel or Stick** — 7 or 8 pixels, code adjustable via `range()` arguments

---

## Research Foundation

This tool is grounded in the following research-based principles:

- **PRIMM Framework** — Sentance, S., Waite, J., & Kallia, M. (2019). *Teaching computer programming with PRIMM: a sociocultural perspective.* Computer Science Education, 29(2–3), 136–176.
- **Cognitive Load Theory** — Sweller, J. (1988). Cognitive load during problem solving: Effects on learning. *Cognitive Science*, 12(2), 257–285.
- **Embodied Cognition** — Physical and visual representations of abstract concepts (such as a pixel lighting up when a loop iterates) reduce cognitive load and improve retention for novice programmers.
- **Worked Examples Effect** — Students learn more effectively when they study worked examples before attempting to solve problems independently.
- **Productive Failure** — Wrong answers are learning opportunities. The Similar Example mechanism ensures students engage with the concept again rather than simply moving past it.

---

## Technology

- Built with **React 18** (via CDN — no build tools or npm required)
- All code uses standard `React.createElement()` — no JSX, no Babel dependency
- Runs entirely in the browser — no server, no database, no login required
- Hosted via **GitHub Pages** — free, permanent, shareable link
- Dark mode supported via CSS media query

---

## Planned Future Concepts

- **Accumulation patterns** — building totals and brightness values across loop iterations
- **loop control: break and continue** — exiting early when a target pixel is reached
- **time.sleep() animations** — adding delays to create visible animation effects on real hardware
- **Random color generation** — using the `random` module to generate dynamic NeoPixel patterns

---

## Related Apps in This Series

| App | Unit | Topic |
|---|---|---|
| PRIMM Python Tutor | Unit 2 | Variables & Data Types |
| PRIMM NeoPixel Loop Tutor | Unit 6 | Loops in CircuitPython |
| *(coming soon)* | Unit 3 | Input & Output |
| *(coming soon)* | Unit 5 | Conditionals |

---

## License

This project was developed for educational use at Charles R. Drew Charter Senior Academy. Teachers and educators are welcome to adapt and use this tool for non-commercial classroom purposes with attribution.

---

*Developed using Claude (Anthropic) as an AI-assisted design and development tool. All curriculum content, pedagogical decisions, physical computing integration, and educational framing by the Drew Charter Engineering & Technology Department.*
