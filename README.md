# Project: Coding? Explain Yourself!

(App description copied from our internal repo's README.md.)

The application facilitates code comprehension assessment for students and progress tracking for teachers. Students will describe given functions in plain English, and Ollama, an open-source LLM, generates code matching their descriptions. The generated code is tested against predefined functions to evaluate comprehension. Key features include user authentication, student and teacher accounts, and a backend comprising an API for data interaction, a code validator for testing generated code, a database for storing user data and submissions, and integration with the Ollama model for code generation.

## Personal contribution highlights

I contributed various features big and small, here is a video demoing 3 biggest ones:

https://youtu.be/o3GTKvYnayI

<iframe width="951" height="579" src="https://www.youtube.com/embed/o3GTKvYnayI" title="cpsc 310 retro" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br><br>
Also contributed Mocha tests (both for Node environment and browser environment), a few async function debugging and fixes, user jailbreak attempt prevention, etc. But those are too fragmented and a bit overwhelming to show in the video.

## Tech Stack:

- React
- Vite
- Node.js
- Express.js
- Nodemon
- Ollama (llama3)
- Mocha
