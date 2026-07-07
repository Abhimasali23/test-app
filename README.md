# test-app

## 1. Project Overview

test-app is a small Node.js command-line quiz application built with native ES modules. The codebase is organized around a simple quiz engine, terminal input helpers, and ANSI-based color utilities for an interactive console experience.

### Runtime and architecture
- **Runtime:** Node.js
- **Module system:** ES modules (`import` / `export`)
- **UI style:** Terminal-based CLI using Node's built-in `readline`
- **Data model:** JSON-backed quiz content with categories, multiple-choice questions, answers, and explanations
- **Dependencies:** No external runtime packages are used by the source files; the app relies on Node.js built-ins only

### Core pieces
- `input.js` contains the `Quiz` class and game flow logic
- `index.js` provides reusable readline prompt helpers
- `colors.js` adds terminal styling via ANSI escape codes
- `questions.json` stores the quiz content used by the app

## 2. File Structure

```text
.
├── colors.js
├── index.js
├── input.js
├── package.json
├── questions.json
└── quiz.js
```

### What each file does
- **colors.js** - ANSI color helpers for success, error, warning, info, and highlighting output
- **index.js** - readline wrappers for prompting, selection, confirmation, and press-enter pauses
- **input.js** - quiz engine with shuffling, scoring, progress tracking, and results rendering
- **package.json** - project metadata and Node.js package configuration
- **questions.json** - question bank grouped into categories
- **quiz.js** - additional quiz question data stored in JSON format

## 3. Setup Instructions

### Prerequisites
- Node.js 18 or newer
- npm installed with Node.js

### Install and prepare the project
```bash
git clone https://github.com/Abhimasali23/test-app.git
cd test-app
npm install
```

### Environment variables
No environment variables are required for the current codebase.

### Create a runnable entry file
The repository currently provides the quiz engine and helpers, but it does not include a dedicated startup script in the inspected files. Create a small entry file such as `app.js` (or `main.js`) that:
1. Imports `createInterface()` from `index.js`
2. Imports `Quiz` from `input.js`
3. Loads question data from `questions.json`
4. Starts the quiz loop and prints results

## 4. Usage Examples

### Run the quiz
After creating your entry file, run it with Node.js:

```bash
node app.js
```

### Typical interaction flow
1. Launch the app
2. Choose a quiz category
3. Answer each multiple-choice question by entering the option number
4. Review correctness feedback and explanations after each response
5. View the final score summary and incorrect answers list

### Manual verification
If you want to validate the core modules individually:
- Import `colors.js` in a small script to confirm ANSI formatting
- Use `index.js` helpers to test prompt/selection behavior
- Instantiate `Quiz` from `input.js` with question data and call `askQuestion()` / `showResults()`

## 5. Additional Technical Details

### Implementation details
- **Question order randomization:** The quiz engine uses the Fisher-Yates algorithm to shuffle questions before play
- **Scoring:** Correct answers increment the score and are tracked in an `answers` array for review
- **Progress display:** A text progress bar shows quiz progress as a percentage
- **Feedback:** The app prints immediate correct/incorrect feedback plus question explanations when available
- **Results summary:** Final output includes category name, total score, performance messaging, and a review of missed questions

### Notable codebase observations
- The repository is intentionally lightweight and avoids external dependencies
- The application is modular, with responsibilities split across input handling, color formatting, and quiz logic
- There is a filename/content mismatch in the inspected files: `index.js` contains input helpers, while `input.js` contains the quiz class logic
- `quiz.js` appears to contain JSON quiz data despite its `.js` extension, so it behaves like a data file rather than executable JavaScript

### Recommended improvement areas
- Add a dedicated entrypoint script so the quiz can be launched without extra setup
- Normalize data file naming (`questions.json` vs. `quiz.js`) to reduce confusion
- Add an `npm start` script and a test script in `package.json` for a smoother developer experience
