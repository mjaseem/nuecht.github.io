---
title: "Formatting as Thinking: Every Element You Reach For Is a Claim About How Ideas Relate"
date: 2024-03-10
topics: [writing, design]
weight: 1
maturity: evergreen
---

The decision to use a heading instead of a paragraph, a list instead of prose, a table instead of description — these are not aesthetic choices. They are claims about how ideas relate to each other.{{< sidenote ref="2024-03-04-on-structure" >}}

Good formatting makes the structure of an argument visible. Poor formatting hides it, or imposes a structure the argument doesn't have. This article demonstrates every formatting element available, in context, so the system can be evaluated at a glance.

---

## Inline Emphasis

Text has several ways to carry weight inline. Each serves a different purpose.

**Bold** signals that something matters here, in this sentence, right now. Use it for terms being defined, warnings, and key claims. *Italics* work for titles, technical terms introduced for the first time, or a softer stress — the kind a speaker achieves with vocal emphasis.

~~Strikethrough~~ marks something deliberately withdrawn: a correction made visible, a retraction that acknowledges what came before. <mark>Highlight</mark> draws the eye to a passage worth returning to later.

`Inline code` is exact. It means: this precise string of characters, not a concept. The moment you're talking about a literal token — a command, a variable name, a file path — reach for the monospace.{{< sidenote ref="2024-03-02-on-code-in-prose" >}}

Keyboard shortcuts read most clearly with semantic markup: press <kbd>⌘</kbd> + <kbd>K</kbd> to insert a link, or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> to open the command palette.

### Links

Links are [citations](https://www.w3.org/). They tell the reader where an idea came from and where to go next. Link the specific phrase that names the concept, not the word "here" or "this article."

---

## Headings

Headings divide text into named regions. The name matters as much as the break. A good heading is specific enough that a reader skimming could reconstruct the argument from headings alone.

### h3 — Section subdivision

Use h3 to subdivide within a major section. When a section has two or more distinct parts, name them. Avoid using h3 as a visual accent — it creates hierarchy the reader will expect to navigate.

#### h4 — Detail within a subsection

Reserve h4 for deeply nested reference material, like documentation with genuine four-level hierarchy. In essays and articles, reaching for h4 usually signals the structure needs rethinking.

##### h5 — Rarely needed

Fifth-level headings appear almost exclusively in long technical specifications. At this depth, consider whether the content would be clearer as a table or a definition list instead.

###### h6 — Structural label

The smallest heading level. Useful as a label within dense reference sections.

---

## Lists

### Unordered lists

For items without natural rank or sequence:

- The visual rhythm of a list changes how quickly readers move through content
- Bullet points flatten hierarchy — every item claims equal weight
- Use prose when items are causally related; use a list when they are parallel

### Ordered lists

For steps, rankings, or items where sequence matters:

1. Write the first draft without editing
2. Let it rest before revising
3. Cut every word that doesn't earn its place

### Nested lists

Nesting works for items with genuine sub-items — but only one level deep in most cases:

- Typography
  - Serif: warmer, better suited to long-form reading
  - Sans-serif: cleaner, better suited to UI and short text
  - Monospace: essential for code; creates visual precision
- Layout
  - Line length: 45–75 characters for comfortable reading
  - Line height: 1.5–1.8 for body text

### Task lists

Used for annotating reading, tracking work, or showing a process in progress:

- [x] Define the problem clearly
- [x] Gather primary sources
- [ ] Write the first draft
- [ ] Revise for clarity and compression
- [ ] Share for feedback

---

## Blockquotes

For quoting another voice, or isolating a key passage that deserves its own space:

> The goal of writing is to make something hard to see — an argument, a feeling, a structure of thought — visible and navigable. Everything else is in service of that.

A block of quoted text dropped without framing asks the reader to do the work of connecting it. Introduce the quote, then draw a conclusion from it.

<div class="callout">
  <span class="callout__label">Note</span>
  <p>Callout boxes work for content that sits adjacent to the main argument — a warning, a definition, an aside that would interrupt the flow if written as a paragraph.</p>
</div>

---

## Code

Code blocks display literal text with syntax preserved. Always specify the language for syntax highlighting.

### Shell

```sh
# Clone the repository and start the development server
git clone https://github.com/username/garden.git
cd garden
hugo server -D
```

### Go

```go
// Fibonacci returns the nth Fibonacci number recursively.
func Fibonacci(n int) int {
    if n <= 1 {
        return n
    }
    return Fibonacci(n-1) + Fibonacci(n-2)
}
```

### CSS

```css
/* Fluid type scale using clamp() for responsive sizing */
--text-base: clamp(1rem, 0.95rem + 0.25vw, 1.125rem);
--text-lg:   clamp(1.2rem, 1.1rem + 0.4vw, 1.4rem);
```

### JSON

```json
{
  "title": "Garden",
  "taxonomies": {
    "topic": "topics"
  },
  "params": {
    "description": "A personal publishing system for long-running research."
  }
}
```

### JavaScript

```js
// Debounce a function to limit how often it fires
function debounce(fn, delay) {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}
```

---

## Tables

Tables work when data has both rows and columns with meaningful headers.{{< sidenote ref="2024-03-01-on-typography" >}} They fail when used to align prose, or when the data has only one meaningful axis.

| Element | Purpose | When to avoid |
|---------|---------|---------------|
| Heading | Names a section; creates scannable structure | Fewer than two sub-items beneath it |
| List | Shows parallel items at equal weight | Items have causal or narrative relationships |
| Table | Compares items across multiple dimensions | Fewer than three rows of real data |
| Blockquote | Gives voice to another source | When paraphrasing rather than quoting |
| Code block | Shows literal, exact text | Describing a concept rather than a specific string |

---

## Images

An image is an argument by demonstration.{{< sidenote ref="2024-03-03-on-visual-thinking" >}} It shows something that would take many sentences to describe — and even then, imprecisely.

Use a `<figure>` element with a `<figcaption>` when the image needs commentary. The caption should not describe what is already visible; it should name what the image is evidence of.

<figure>
  <img src="https://picsum.photos/seed/writing/1200/600" alt="A warm, minimal desk with paper and a notebook open to a blank page">
  <figcaption>The physical act of writing and the digital act are more similar than they appear. Both require choosing what to leave out.</figcaption>
</figure>

Images without captions sit naturally in the prose flow when no commentary is needed:

![An abstract close-up of paper texture and grain](https://picsum.photos/seed/paper/800/400)

Multiple images can document a progression or comparison:

<figure>
  <img src="https://picsum.photos/seed/typography/1200/500" alt="A spread of printed pages showing typographic layout">
  <figcaption>Typographic decisions made at the system level — type scale, line height, measure — cascade into every page of a long document.</figcaption>
</figure>

---

## Video

Embedded video expands what writing can do. A short demonstration communicates things no amount of prose can. Use it when showing matters more than describing.

<div class="video-embed">
  <iframe
    src="https://www.youtube.com/embed/jNQXAC9IVRw"
    title="Example embedded video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
  </iframe>
</div>

---

## Horizontal Rules

A horizontal rule creates a hard visual break — stronger than a heading. It says: *we are starting something genuinely new*. Use it sparingly. Once or twice in a long piece, only when sections are truly discontinuous in subject or register.

---

*This article is itself a demonstration of every element described. The structure you've just navigated was built from nothing but the elements above.*
