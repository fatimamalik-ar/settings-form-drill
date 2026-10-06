# WORKFLOW.md

## Setup
I built the same settings form twice. Round one used one lazy sentence: "Make a settings form with validation." Round two used a fresh chat and a precise prompt with fields, rules, example behavior, edge cases, and an instruction to plan first, then write and run tests. The code is on the branches round-one and round-two.

## Correctness
Round one accepted "a@b" as a valid email and accepted a name made only of spaces. I caught both by testing by hand. Round two's prompt named both cases, and it rejected "a@b". It also produced test.html, and the AI reported 11/11 tests passing. Round one had no tests, so only my manual checking verified its validation.

## Accessibility
This was closer than I expected. Round one had 27 aria- lines and round two had 24, and focus was visible in round one when I pressed Tab. So the vague prompt was not clearly worse here, and the aria count alone does not prove quality. The difference is that round two's prompt required linked labels, role="alert" errors, and focus moving to the first invalid field, so those features were guaranteed instead of left to chance.

## Edge cases
Round one missed two: very short emails like "a@b" and whitespace-only names. Round two handled the edge cases I listed in the prompt, including an empty optional password. I did not test edge cases I forgot to list.

## Review effort
Round one: 17 steps and 3m59s of AI time, plus manual testing that found two bugs I would still need to fix. Round two: 28 steps and 3m14s, so more steps but less time, and the tests did part of my checking. Counting fixing time, round two is faster end to end.

## AI mistake I caught
Round one's AI said it validated email format, but it accepted "a@b". It also accepted a whitespace-only name.

## Lesson
A vague prompt gives code that looks right. A precise prompt with a test step gives code I can check.