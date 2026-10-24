# Copilot instructions

## Project structure and architecture

- The app is a standalone web page in `index.html`; HTML, CSS, question data, and JavaScript behavior all live in that file.
- The quiz flow is managed in the page script: `questions` is the content source, `renderQuestion()` updates the view, `selectAnswer()` handles scoring and feedback, and `showResults()` presents the final score and reaction.
- The interface has intro, quiz, and results sections. The `.hidden` class switches between them; quiz state is held in `currentIndex`, `score`, and `answered`.
- Styling is driven by CSS custom properties. The `prefers-color-scheme: dark` rule overrides the light theme, including the pink mission-question panel. `prefers-reduced-motion` reduces animation and transition durations.

## Build, test, and lint

- There is no package manifest, build step, test runner, or lint command. The page has no server or external dependencies; open `index.html` directly in a browser.
- For a manual smoke test, start from the intro, complete all 10 questions, check that correct answers increase the score and incorrect answers do not, then verify feedback, progress, final results, and replay.
- To check one answer path in isolation, reload `index.html`, start a new mission, and select an answer on the first question; there is no automated single-test command.

## Code conventions

- Keep the app self-contained: do not add a framework, dependency, server requirement, or separate asset unless the project scope changes.
- Keep quiz content in the `questions` array. Each entry has a `category`, `question`, four `answers`, a zero-based `correct` index, and an explanatory `fact`.
- Preserve the three-screen flow and update state through the existing render/answer/result functions rather than duplicating quiz logic in event handlers.
- Keep theme colors in the existing CSS custom properties and provide corresponding values in both the light `:root` and dark-mode override when adding colors.
- The page UI and quiz content are in Spanish (`lang="es"`). Preserve semantic headings, button-based answer choices, the live feedback region, progress-bar ARIA values, and question-title focus when rendering a new question.
