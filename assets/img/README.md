# Images for this site

Drop image files straight into this folder. Nothing needs configuring.

## Naming

Use a unit prefix, then a short description, all lowercase with hyphens:

```
u1-particle-states.png
u1-heating-curve.png
u3-solar-system-scale.jpg
header-unit-2.jpg
```

The prefix keeps the folder sorted by unit as it grows, and lowercase hyphenated
names avoid the broken-link problems that spaces and capitals cause on web servers.

## Formats and sizes

| Kind of image | Format | Aim for |
|---|---|---|
| Photo-like, AI generated illustration, scene | `.jpg` | under 300 KB |
| Flat colour, diagram, screenshot, anything with text | `.png` | under 300 KB |
| Logo or simple shape you may rescale | `.svg` | any |

Keep the longest edge at about 1600 pixels. Anything larger just slows the page
down on a phone without looking better. If a file comes out at several megabytes,
resize it before committing, because every visitor downloads the whole thing.

## Putting an image on a page

Open the unit's `index.html` and paste one of these blocks where you want it.
The site stylesheet already handles sizing, borders, and print behaviour.

A normal figure with a caption:

```html
<figure>
  <img src="../assets/img/u1-particle-states.png"
       alt="Diagram comparing particle arrangement in a solid, a liquid, and a gas">
  <figcaption>Particles in the three states of matter.</figcaption>
</figure>
```

A banner across the top of a unit page:

```html
<div class="hero">
  <img src="../assets/img/header-unit-2.jpg" alt="">
</div>
```

Two or three images side by side:

```html
<div class="img-row">
  <figure>
    <img src="../assets/img/u1-melting.jpg" alt="Ice melting in a beaker">
    <figcaption>Melting</figcaption>
  </figure>
  <figure>
    <img src="../assets/img/u1-boiling.jpg" alt="Water boiling in a beaker">
    <figcaption>Boiling</figcaption>
  </figure>
</div>
```

Note the `../` at the front of the path. Unit pages live one folder down, so they
have to step back up to reach `assets`. From a page at the site root, drop the
`../` and write `assets/img/...`.

## Alt text

The `alt` attribute is what a screen reader announces and what shows if the image
fails to load. Describe what the image shows, not what it is called:

- Good: `alt="Heating curve for water with flat sections at 0 and 100 degrees"`
- Poor: `alt="heating curve image"`

If an image is purely decorative and carries no information, use `alt=""` so
screen readers skip it rather than reading out a filename.

## A caution on generated images

AI image tools are good at illustration and poor at accuracy. Text inside a
generated image is usually garbled, and structural details drift: wrong number of
organelles, mislabelled parts, particles spaced wrongly for the state they claim
to show. Students take whatever the picture shows as fact, errors included.

Use generated images for atmosphere, scene setting, and unit headers. For anything
a student will read as content, either check it carefully against a reliable source
or use a hand-built SVG diagram where every label is under your control.
