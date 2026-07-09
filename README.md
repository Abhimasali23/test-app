# test-app

## Overview
`test-app` is a lightweight Node.js command-line quiz application built with ES modules and standard terminal I/O. The project uses Node’s built-in `readline` interface to collect user input and ANSI color helpers to improve the quiz experience in the terminal.

This repository contains the core application files:
- `index.js`
- `input.js`
- `quiz.js`
- `colors.js`
- `questions.json`
- `package.json`

No README existed previously, so this document provides the initial project overview and setup guidance.

## Features
- **Terminal-based quiz flow**: Runs entirely in the command line and guides the user through quiz questions interactively.
- **User input handling with `readline`**: Uses Node’s built-in terminal input API to capture answers from the user.
- **ANSI-colored output**: Applies color formatting in the terminal to make prompts, feedback, and results easier to read.
- **Question-driven content**: Loads quiz content from `questions.json`, separating application logic from quiz data.
- **Modular ES module architecture**: Splits responsibilities across dedicated files for startup, input handling, quiz logic, and color utilities.
- **Node.js runtime support**: Designed for execution in a standard Node.js environment without a front-end framework.
- **Simple CLI execution model**: Intended to be launched directly from the terminal with a Node.js command.

## Repository Structure
```text
test-app/
├── colors.js
├── index.js
├── input.js
├── package.json
├── questions.json
└── quiz.js
```

## Prerequisites
- **Node.js** installed locally
- **npm** available if you want to install package metadata or dependencies listed in `package.json`

## Installation
1. **Clone the repository**
   ```bash
   git clone https://github.com/Abhimasali23/test-app.git
   cd test-app
   ```

2. **Install package dependencies**
   ```bash
   npm install
   ```
   > Note: no lockfile was detected in the repository analysis, and package contents were not fully extracted. This step is still recommended to ensure the local environment matches the package configuration.

## Usage
1. Start the quiz application from the project root:
   ```bash
   node index.js
   ```

2. Follow the terminal prompts to answer the quiz questions.

3. The application will use colored output in the terminal to display quiz messages and feedback.

## Configuration Notes
- **Quiz content**: Edit `questions.json` to add, remove, or update quiz questions.
- **Terminal styling**: Update `colors.js` to adjust ANSI color behavior or formatting helpers.
- **Application flow**: `quiz.js` appears to control the quiz logic, while `input.js` handles user interaction and `index.js` serves as the entry point.
- **Module system**: The project uses ES modules (`import` / `export`), so any additional files should follow the same style.
- **Package metadata**: `package.json` defines the Node.js package configuration; exact scripts were not reliably extracted, so use direct Node execution unless you confirm a script locally.

## Contribution Guidance
1. Fork the repository.
2. Create a feature branch for your changes.
3. Make updates in the appropriate file:
   - `quiz.js` for quiz logic
   - `input.js` for terminal input behavior
   - `colors.js` for terminal styling
   - `questions.json` for quiz data
4. Test your changes locally with Node.js.
5. Open a pull request with a clear description of the updates.

When contributing, keep the project lightweight, maintain the ES module structure, and avoid introducing unnecessary dependencies unless they are required by the application.