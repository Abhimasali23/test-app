# test-app

## Project Title
A small Node.js command-line quiz application built with ES Modules and interactive terminal prompts.

## Overview
This repository contains an interactive quiz app that runs in the terminal. It uses Node.js built-in `readline` support to prompt the user, collect answers, confirm actions, and pause between screens. The app is organized around a `Quiz` class that manages question order, score tracking, feedback for each answer, progress display, final results, and review of incorrect answers.

The project demonstrates modern JavaScript features such as:
- ES Module syntax (`import` / `export`)
- JSON-based content loading for quiz data
- Class-based state management
- Array shuffling and iterative control flow
- Terminal UI formatting with custom ANSI color helpers

## Features
- **Interactive CLI quiz flow**: Runs entirely in the terminal with prompts, selections, confirmations, and pauses.
- **Quiz state management**: Tracks current question, score, and overall progress through a dedicated `Quiz` class.
- **Randomized question order**: Shuffles questions to provide a different experience each run.
- **Immediate answer feedback**: Shows whether the user’s answer was correct or incorrect after each question.
- **Final score and summary**: Presents the user’s results at the end of the quiz.
- **Incorrect answer review**: Reviews questions answered incorrectly so the user can see what they missed.
- **Category-based question bank**: Loads questions from `questions.json` with categories such as JavaScript, Node.js, and General.
- **Terminal color output**: Uses custom ANSI color utilities for a more readable and polished CLI experience.
- **Reusable input helpers**: Centralized readline helpers for prompting, selection, confirmation, and pausing.
- **No frontend or build tooling required**: The app is designed to run directly in Node.js.

## Tech Stack
- **Runtime**: Node.js
- **Module system**: ES Modules
- **CLI interface**: Built-in `node:readline`
- **Data format**: JSON
- **Styling in terminal**: ANSI escape codes via custom helper functions
- **Architecture**: Small, file-based modular structure

## Project Structure
```text
test-app/
├── colors.js
├── index.js
├── input.js
├── package.json
├── questions.json
└── quiz.js
```

## Getting Started

### Prerequisites
- Node.js installed locally
- A terminal capable of displaying ANSI color output
- npm available if you want to install project dependencies from `package.json`

## Installation
```bash
git clone https://github.com/Abhimasali23/test-app.git
cd test-app
npm install
```

## Usage / Run Commands
Run the quiz from the project root with Node.js:

```bash
node index.js
```

If your local setup or entry point is configured differently, you can also inspect and run the app’s main executable file directly as needed.

## How It Works
1. **`index.js`** starts the application and wires together the quiz flow.
2. **`input.js`** creates and manages the readline interface, exposing helpers for:
   - prompting for input
   - selecting from options
   - confirming actions
   - pausing between steps
3. **`quiz.js`** contains the `Quiz` class, which:
   - loads and shuffles questions
   - advances through the quiz
   - checks user answers
   - updates score and progress
   - prints final results
   - reviews incorrect answers
4. **`questions.json`** stores the quiz content in categorized form.
5. **`colors.js`** provides ANSI color formatting helpers for a better CLI presentation.

## Question Categories
The question bank is organized into categories, including:
- **JavaScript**
- **Node.js**
- **General**

This makes it easy to expand the quiz with more topic areas or filter questions by category in the future.

## Customization
- **Add or edit questions** in `questions.json`
- **Create new categories** by extending the JSON structure
- **Adjust terminal styling** in `colors.js`
- **Modify quiz behavior** in `quiz.js`, such as:
  - shuffle logic
  - scoring rules
  - feedback text
  - review flow
- **Update prompt behavior** in `input.js` to change how users interact with the quiz

## License
No license information is currently specified in the repository.

## Contributing
Contributions are welcome. If you plan to extend the app, consider opening a pull request with a clear description of the change.