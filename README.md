# Targets Unlimited Outdoors — homepage concept

A static homepage concept for an outdoor and shooting-sports retailer.
Open `index.html` in a browser. No build step, no dependencies, no server.

**Live preview:** see the GitHub Pages link on this repository.

## What it is

A single self-contained page: hand-written HTML and CSS, one small vanilla-JS
module for the hero carousel. Product data and imagery come from the retailer's
public catalog endpoints and are stored locally in `assets/`, so the page is
portable and works offline.

This is a design concept, not a working store. Navigation and cart controls are
inert by design.

## Structure

1. Utility bar — shipping promise, Military/LEO offer, contact
2. Header with category-scoped search
3. Primary navigation, five entry points
4. Hero carousel — four campaigns
5. Category rail — twelve tiles, with an agency and bulk enquiry strip
6. Deals
7. Seasonal campaign slot
8. Fishing department
9. Merch
10. Military, law enforcement and first responder discount
11. Customer reviews
12. Email capture
13. Footer

## Hero carousel

Four campaigns, each rendering its own background wall from that campaign's
products, so every frame demonstrates range rather than showing a generic banner.

Behaviour:

- rotates every 7 seconds
- pauses on hover, on keyboard focus, and when the tab is hidden
- stops permanently on any click or arrow key, so the visitor stays in control
- no auto-advance under `prefers-reduced-motion`
- arrows and dots are real buttons, keyboard reachable, with ARIA labels
- all slides remain in the DOM so their content stays indexable

To add a campaign: duplicate an `<article class="slide">`, set its `--accent`
and `--cta` custom properties, point the wall at that campaign's images, and add
a matching `.dot` button. The script picks up the new count automatically.

## Seasonal campaign slot

`<section class="ev">` is built to be swapped each season. Change `--event` in
the stylesheet, then replace the ribbon, copy and three product cards. Remove the
section and its stylesheet block to retire it.

## Design notes

- Two typefaces only: Big Shoulders Display for headings, Barlow for body
- One job per colour: red for purchase actions, blaze orange for campaigns
- The hero occupies roughly half the viewport, leaving the category rail visible
  on first paint
- One carousel on the page, and it yields to the visitor on first interaction
- Responsive to 390px, visible keyboard focus, reduced motion respected

## Files

```
index.html        the page
assets/           product imagery
README.md
```
