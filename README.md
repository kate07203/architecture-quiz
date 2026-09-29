# Architecture quiz

Open `index.html` in any modern browser. No installation, server, or internet connection is needed for the quiz. The optional source link needs internet.

## How the files work together

- `index.html` supplies the content: the building photograph, question, four buttons, and explanation. The `link` loads the CSS; the deferred `script` loads JavaScript after the HTML has been read.
- `style.css` controls colors, type, spacing, and layout. Grid creates two columns. The media query stacks them on narrow screens. `.correct` and `.incorrect` style answer states.
- `script.js` makes the quiz respond. Its numbered comments walk through the process.

## Follow a click through the code

1. `querySelectorAll('.answer')` collects all four answer buttons.
2. `addEventListener('click', checkAnswer)` tells each button which function to run when clicked. Native buttons also work with Enter and Space.
3. `event.currentTarget` identifies the button. `dataset.architect` reads its HTML `data-architect` value.
4. `===` compares that value with `correctAnswer`, producing `true` or `false`.
5. `if / else` chooses the feedback. `textContent` updates the message; `classList.add` changes the appearance.
6. `explanation.hidden = false` reveals the architectural clues for either outcome. Buttons are disabled to preserve the attempt.
7. Try again clears the message, removes the colors, enables the buttons, and returns keyboard focus to the first answer.

The feedback region uses `role="status"` so assistive technology can announce the result. Written feedback communicates correctness independently of color.

## Try a small edit

Change `--paper` in the CSS to update the page background. Edit the heading in HTML to change the question's wording. To use a different building, update the photograph, building details, answer labels AND their `data-architect` values, the `correctAnswer` constant, feedback messages, explanation, and source link together.

The photograph is stored locally as `fallingwater.jpg`. HTML's `<img src="fallingwater.jpg">` loads it, and `alt` supplies a written description for screen readers. CSS's `width: 100%` and `height: auto` scale the full photograph proportionally without cropping. Clicking the photograph opens the full-resolution image in a new tab.

Photo: Lykantrop, April 4, 2007, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Frank_Lloyd_Wright_-_Fallingwater_exterior_1.JPG). The source permits unrestricted use, redistribution, and modification (Copyrighted free use). The downloaded version includes Steve Morgan's leveling and highlight adjustments; no additional image edits were made for this quiz.

Sources: [Designing Fallingwater](https://fallingwater.org/history/the-kaufmanns-fallingwater/designing-fallingwater/) and [Preservation history](https://fallingwater.org/preservation-history/).


## Answer-specific visual feedback

Previously, the `else` branch gave the same correction for every wrong choice. It now uses `comparisons[selectedAnswer]` to retrieve content matched to that choice. For example, `comparisons['Zaha Hadid']` returns the Heydar Aliyev Center comparison.

- **HTML:** `#comparison` is a hidden section with empty text elements and an image. This gives all three comparisons the same readable structure.
- **JavaScript:** `comparisons` stores a building name, image filename, alt text, explanation, photo credit, license, and source links for each wrong architect. `showComparison()` fills the HTML using `textContent`, `src`, `alt`, and `href`, then sets `hidden = false`. The live feedback also includes a concise comparison so screen-reader users hear the educational correction immediately.
- **CSS:** `#comparison` styles the card. `width: 100%` and `height: auto` display the complete photograph at the available width.
- **Reset:** hides the comparison and removes its image source. The next wrong answer populates the same card with fresh content; a correct answer keeps it hidden.

The comparison photos are local, so they work offline. Click any photo for a full-size view. The comparisons teach visible features of these specific projects, rather than implying each architect uses only one style.

### Comparison photo credits

- hadid.jpg: Heydar Aliyev Center · Baku. Photo by Avisadehh, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). [Image source](https://commons.wikimedia.org/wiki/File:HEIDAR_ALIYEV_CENTER_WIDE_ANGLE.%D7%96%D7%95%D7%95%D7%99%D7%AA_%D7%A8%D7%97%D7%91%D7%94_%D7%9E%D7%A8%D7%9B%D7%96_%D7%94%D7%99%D7%99%D7%93%D7%A8_%D7%90%D7%9C%D7%99%D7%99%D7%91.jpg). Unmodified. [Architecture reference](https://www.zhfoundation.com/collections/heydar-aliyev-centre/).

- corbusier.jpg: Villa Savoye · Poissy. Photo by Valueyou, [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). [Image source](https://en.wikipedia.org/wiki/File:VillaSavoye.jpg). Unmodified. [Architecture reference](https://www.villa-savoye.fr/en/discover/le-corbusier-s-5-points-of-modern-architecture).

- gehry.jpg: Guggenheim Museum Bilbao · Bilbao. Photo by Zarateman, [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). [Image source](https://commons.wikimedia.org/wiki/File:Bilbao_-_Guggenheim_40.jpg). Unmodified. [Architecture reference](https://www.guggenheim-bilbao.eus/en/about-the-museum/the-museum).
