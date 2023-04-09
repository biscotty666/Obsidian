---
bg: blue
---

#### Hello from Cover Page

---

Greetings from second slide.

--

#### This is a vertical slide

---

#### These are some annotations

<style>
	.with-border{
		border: 1px solid red;
	}
</style>
text with border <!-- element class="with-border" -->

text with border <!-- element style="border: 1px solid green" -->

text with background <!-- element style="background:blue" -->

text with attribute <!-- element data-toggle="modal" -->

---

<!-- .slide: style="background-color: coral;" -->

# Header with coral background color

Paragraph has coral background color, too!

---

::: block

#### Header
_and_
Paragraph content
*in same block*

:::

---
### block can be used to scope styles

no color

::: block <!-- element style="background-color: red;" -->

everything inside this block has red background color

::: block <!-- element style="background-color: blue;" -->

blue

:::

red

:::

no color

[mszturc.github.io/obsidian-advanced-slides/extend-syntax/blockcomment/](https://mszturc.github.io/obsidian-advanced-slides/extend-syntax/blockcomment/)

---

Fade in <!-- element class="fragment" -->

Fade out <!-- element class="fragment fade-out" -->

Highlight red <!-- element class="fragment highlight-red" -->

Fade in, then out <!-- element class="fragment fade-in-then-out" -->

Slide up while fading in <!-- element class="fragment fade-up" -->

---

- Permanent item
- Appear Fourth <!-- element class="fragment" data-fragment-index="4" -->
- Appear Third <!-- element class="fragment" data-fragment-index="3" -->
- Appear Second <!-- element class="fragment" data-fragment-index="2" -->
- Appear First <!-- element class="fragment" data-fragment-index="1" -->

---

<!-- slide bg="aquamarine" -->
## Slide color text based background

---

[<!-- slide bg="https://picsum.photos/seed/picsum/800/600" -->
## Slide with image background

---

<!-- slide bg="https://picsum.photos/seed/picsum/800/600" data-background-opacity="0.5" -->
## Slide with image background

---

## My Slide

This is part of my Presentation


note: this is not! Only the speaker might see this text.

- and this bulletpoint
- or this picture

![](https://picsum.photos/id/1005/250/250)>)
