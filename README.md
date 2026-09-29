# Architecture Quiz — Who Designed This Building?

## Original idea

I want to create a one question quiz for architecture students that are trying to learn famous architects and their signature design styles using HTML, CSS, and JavaScript. The user should identify the architect of a famous building from a multiple choice list and receive feedback if right or wrong -- explaining the architectural clues behind the right answer. When someone selects an answer, the experience should immediately tell them whether they are correct and explain why. Please help me create this as a small browser-based version. Keep the code beginner-friendly and help me understand the happenings in the code.

## Opening and running the project

1. Download this repository using **Code → Download ZIP** on GitHub, then unzip it. Alternatively, clone it with `git clone https://github.com/kate07203/architecture-quiz.git`.
2. Open the extracted project folder.
3. Double-click `index.html` to open it in a modern browser.
4. Select an architect to see immediate feedback. If your answer is incorrect, a photograph and explanation compare that architect’s work with Fallingwater. Select **Try again** to reset the quiz.

Keep the HTML, CSS, JavaScript, and four JPG files together in the same folder. No installation, build command, or server is required. The quiz and photographs work offline; external reference and credit links require internet access. The GitHub repository contains the source files; it is not a hosted version of the quiz.

## AI tool used

**OpenAI Codex (desktop app)** helped generate and revise the HTML, CSS, and JavaScript, explain how the code works, and check the interaction. I supplied the concept, tested the experience, and directed the content and visual revisions. The building photographs are real photographs from the credited sources below, not AI-generated images.

## Selected prompts

The following excerpts are from my prompts to Codex, in the order of the main revisions.

### 1. Build the first version

> I want to create a one question quiz for architecture students that are trying to learn famous architects and their signature design styles using HTML, CSS, and JavaScript. The user should identify the architect of a famous building from a multiple choice list and receive feedback if right or wrong -- explaining the architectural clues behind the right answer.

> Keep the code beginner-friendly and help me understand the happenings in the code.

### 2. Use a real photograph

> The current illustration of Fallingwater feels too generic and hard for students to actually learn what the architectural elements look in actuality. Can we please change it to be an actual real life image of Fallingwater?

### 3. Make incorrect answers educational

> I think that the clues that it gives students about organic architecture and some key elements that make this building true to Frank Lloyd Wright is great. But, instead of simply saying "Not quite. You chose Zaha Hadid. The correct answer is Frank Lloyd Wright," I want the quiz to help the person learn something why this is. Can we make the feedback explain how the wrong architect chosen is different from the correct architect? Include an image of the wrong architect's style so it is clear to see the differences. Show me what needs to change and explain why.

### 4. Refine the visual design

> I want to change the design of the site a bit to feel more "aesthetic and architectural," so can you please make the site feel like a minimalist architecture portfolio rather than this generic online Codex quiz. Make sure there is a lot of white space, make the typography, be very simple, keep the colors to be black/white/gray, and have a clear hierarchy. Do not change anything else of the interaction/keep the interaction the main focus. Show me what changes in the code and explain why.

### 5. Clarify the instructions

> I found an error while testing this out. In the bio under "Who designed this building," it says "Choose an architect to reveal the story"....as a student I feel like that would confuse me the purpose of the quiz, because this is not about storytelling. So, please change "Choose an architect to reveal the story" to "Chose the correct architect that designed this building."

### 6. Label the answers explicitly

> I found one final visual design edit to be made. Right now when you click on the wrong architect their name is in grey and the correct architect is in black. While the bottom description helps understand why, to more easily show that the answer is wrong, please add "incorrect" next to each architect that is wrong when you click on it. And please add "correct" to the right architect's name.

## My reflection

My original intention was to create a simple one-question quiz to help architecture students learn about famous architects and be able to recognize elements of their signature design styles. The first change I made was to change the illustration of Fallingwater to an actual picture of the building so students knew what it looked like in real life. After this edit, the first version was complete and successfully allowed users to identify the architect of Fallingwater and provided immediate feedback. But after testing it, I realized that simply telling a student that their answer was wrong did not actually help them understand why it was wrong. So I asked Codex to help me revise the quiz so that when a user selects an incorrect architect, they see an example of that architect's work alongside an explanation comparing their design style to Frank Lloyd Wright's. Finally, I changed the visual design of the quiz to be more true to architecture → it now resembles a minimalist architecture portfolio and I also revised some of the language and answer feedback after noticing that parts of the interface could be clearer for a student using the quiz.

In this assignment AI helped me translate my ideas into HTML, CSS, and JavaScript and helped explain how changes to the code affected the interaction. I still had to decide what the experience should teach and evaluate whether the AI-generated result actually accomplished that goal. For example, AI initially created generic incorrect-answer feedback, but I decided that comparing the selected architect's work visually with Fallingwater would make the mistake itself part of the learning experience. I also noticed through testing that the phrase "Choose an architect to reveal the story" did not accurately communicate the purpose of the quiz, so I changed it to give the user clearer instructions. One thing I learned through this process is that AI is magical!!! and can create and revise the code quickly, but it ultimately cannot decide for me whether the experience was effective for my intended user. I had to continue testing the quiz from the perspective of an architecture student and direct the AI toward changes that better matched my original intention.


## How the files work together

- `index.html` supplies the content: the building photograph, question, four buttons, and explanation. The `link` loads the CSS; the deferred `script` loads JavaScript after the HTML has been read.
- `style.css` controls colors, type, spacing, and layout. Grid creates two columns. The media query stacks them on narrow screens. `.correct` and `.incorrect` style answer states.
- `script.js` makes the quiz respond. Its numbered comments walk through the process.

