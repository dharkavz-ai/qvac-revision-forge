# QVAC Revision Forge

A local AI study tool that turns raw study notes into focused revision packs using Tether's QVAC SDK.

QVAC Revision Forge runs AI inference locally on the device. It does not send study notes to a cloud AI service.

## What It Does

Paste your study notes and Revision Forge generates a structured revision pack containing:

- **Core Idea** — a concise summary of the main topic
- **Key Concepts** — the most important ideas from the notes
- **Common Mistake** — a potential misunderstanding based on the provided notes
- **Quiz** — 3 multiple-choice questions with 4 choices each
- **Answer Key** — answers for the generated questions

The app is designed to turn unstructured study material into something easier to review.

## QVAC SDK

This project uses:

- **QVAC SDK:** `@qvac/sdk` `0.19.1`
- **Model:** `LLAMA_3_2_1B_INST_Q4_0`
- **QVAC functions:** `loadModel()`, `completion()`, and `unloadModel()`

The application loads the QVAC model locally and uses `completion()` to generate the revision pack.

## Features

- Local AI inference
- Browser-based interface
- Command-line interface
- Streaming AI output
- Source-focused revision generation
- No cloud AI API required
- Simple Node.js setup

## Requirements

- Node.js
- npm
- A computer capable of running the selected local model

## Installation

Clone the repository:

```bash
git clone https://github.com/dharkavz-ai/qvac-revision-forge.git
cd qvac-revision-forge
```

Install dependencies:

```bash
npm install
```

## Run the Web App

Start the application:

```bash
npm start
```

Then open:

```text
http://localhost:3000
```

Paste your study notes into the text box and generate your revision pack.

## Run the Command-Line Version

You can also use Revision Forge directly from the terminal:

```bash
npm run forge
```

Paste your study notes into the terminal.

When you are finished entering your notes, type:

```text
EXIT
```

The application will load the local QVAC model and generate the revision pack.

## How QVAC Is Used

The core inference flow is:

```text
Study Notes
    ↓
QVAC loadModel()
    ↓
Local LLM
    ↓
QVAC completion()
    ↓
Revision Pack
    ↓
QVAC unloadModel()
```

The application uses QVAC to load a local model and generate the revision pack directly on the user's device.

## Project Structure

```text
qvac-revision-forge/
├── app.js          # Command-line interface
├── server.js       # Web server and QVAC inference
├── package.json    # Project configuration and dependencies
├── quickstart.cmd  # Windows quickstart
├── LICENSE.txt     # MIT License
└── README.md       # Project documentation
```

## Example

### Input

```text
Photosynthesis is the process by which green plants use
light energy to convert carbon dioxide and water into
chemical energy stored as glucose. Oxygen is released
as a by-product.
```

### Generated Revision Pack

```text
CORE IDEA

Photosynthesis uses light energy to convert carbon dioxide
and water into chemical energy stored as glucose.

KEY CONCEPTS

1. Light energy
2. Carbon dioxide
3. Water
4. Glucose
5. Oxygen

COMMON MISTAKE

Confusing glucose with oxygen. Glucose is the chemical
energy storage product described in the notes, while
oxygen is released as a by-product.

QUIZ

1. What process is described in the notes?

A. Photosynthesis
B. Respiration
C. Digestion
D. Fermentation

2. What is stored as chemical energy?

A. Water
B. Oxygen
C. Glucose
D. Carbon dioxide

3. What is released as a by-product?

A. Glucose
B. Oxygen
C. Water
D. Light

ANSWER KEY

1. A
2. C
3. B
```

## Why I Built It

I built QVAC Revision Forge to explore how local AI can be used to turn everyday study notes into useful revision material while keeping the inference on the user's device.

## Open Source

This project is released under the MIT License.

## Project Status

Built as an open-source project for the QVAC SDK challenge.

## Repository

https://github.com/dharkavz-ai/qvac-revision-forge