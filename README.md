# Project: Coding? Explain Yourself!

## Introduction

The application facilitates code comprehension assessment for students and progress tracking for teachers. Students will describe given functions in plain English, and Ollama, an open-source LLM backend and API, generates code matching their descriptions. The generated code is tested against predefined functions to evaluate comprehension. Key features include user authentication, student and teacher accounts, and a backend comprising an API for data interaction, a code validator for testing generated code, a database for storing user data and submissions, and integration with the Ollama model for code generation.

*Note: This app description was copied from our internal repo's README.md. Said repo was downloaded from UBC GitHub space and then uploaded to a repo under my GitHub account on this site, but is kept private. The reason is to protect IP rights and respect the university's academic conduct considerations.*

## Contributors

Here is a mapping of contributors in the Git commit history to their accounts in this public GitHub site domain.

- samuel78 - [github.com/masvsal](https://github.com/masvsal)
- Richard - [github.com/richardc412](https://github.com/richardc412)
- Brandon Kato - [github.com/btkato](https://github.com/btkato)
- Vivaan Wadhwa - [github.com/VivaanWadhwa](https://github.com/VivaanWadhwa)
- jduan06 - [github.com/eerieA](https://github.com/eerieA) (self reference)

## Revised demo video (4 months later)

Video on Youtube (5m 40s):

[<img alt="screenshot" src="/resources/Retro 2 screenshot.gif" width="320">](https://youtu.be/QplI0PaIAOo)

This was done 4 months later. After adding a streaming chat box feature, I did a concise retrospective showcasing all the main features the team completed within the allotted time. This is a more polished video trying to include everyone's contributions.

## Individual contribution

Here is a video showing 3 biggest contributions by me.

Video on Youtube (15m 42s):

[<img alt="screenshot" src="/resources/cpsc 310 retro screenshot.png" width="320">](https://youtu.be/o3GTKvYnayI)

This was done right after the official completion date, so it was not a very polished video.

Other individual contributions:
- Mocha tests (both for Node environment and browser environment).
- Async back-end function debugging and fixes.
- Simple user jailbreak attempt prevention.
- Other bug fixes and integration tests.

But those are too fragmented and a bit overwhelming to show in the video.

## Tech stack

- React, Vite, Express.js, Nodemon
- Node.js
- Ollama (llama3)
- Mocha

## Commit statistics

There is a gitstats.json generated by using `gitstats` tool (https://github.com/dmitryn/GitStats). It can be visualized through their web tool https://gitstat.com/ (as of Aug 4 2024).

Here is a screenshot of the `lines added + deleted` page from the visualized result made on Aug 4 2024 (official completion date):

<img alt="screenshot" src="/resources/gitstats vis.jpg" width="540">

, where `jduan06` was my account under UBC GitHub organization.
