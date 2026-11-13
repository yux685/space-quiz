# Copilot instructions

## Project shape

This is a static, single-file quiz. `space-quiz.html` contains the markup, styles, question data, and browser-side behavior; open the file directly in a browser to preview it.

## Architecture and conventions

- The `questions` array is the source of truth for quiz prompts, answer choices, correct-answer indexes, and explanations. `renderQuestion()` builds the current choices; `selectAnswer()` handles feedback, score, and progress; the next/restart handlers advance or reset the quiz; `showResults()` renders the final score.
- Keep presentation in the inline stylesheet and quiz behavior in the inline script; there is no separate application or asset pipeline.
- Theme colors are CSS custom properties defined for the default, explicit dark, and system-preference dark themes. Theme changes should preserve those three modes.
- Quiz choices and actions are native buttons. Preserve keyboard focus transitions, including programmatic focus on `#question-text` (`tabindex="-1"`), and keep the progress bar's ARIA value and text synchronized with quiz progress.
- Layout adapts at the 520px breakpoint, and animations must continue to respect `prefers-reduced-motion`.
- Open `space-quiz.html` directly for browser checks; no server is required.
