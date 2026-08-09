# Lab 2 — Reflection

**Student Name:** Mphatso Kenani
**Student ID:** BECE/21/SS/009

---

### 1. Selector conflict — `p { color: red }` vs `.intro { color: blue }` on `<p class="intro">`

The text will be **blue**. Even though the element selector `p` matches the tag, the class selector `.intro` is more specific than an element selector, so it wins regardless of the order the rules are written in. This is the basic idea behind CSS specificity: the browser doesn't just apply rules top-to-bottom — it ranks them by how specific the selector is (element < class < ID), and the most specific one that matches gets applied. If both rules had used element or both had used class selectors, then the one written last in the stylesheet would win instead.

### 2. `rem` units and accessibility

`rem` stands for "root em" — it means the size is relative to the font-size set on the root `<html>` element (normally 16px by default), not relative to a fixed pixel value. This matters for accessibility because if a visually impaired user increases their browser's default font size (say to 20px), every element sized in `rem` scales up proportionally along with it, keeping the whole page readable and properly proportioned. Text sized in fixed `px` values ignores that browser setting completely and stays the same size, which can leave a user stuck with text that's too small to read comfortably. So if the browser default changes to 20px, a paragraph set to `1rem` would now render at 20px instead of 16px, while a `16px` paragraph would stay at 16px no matter what.

### 3. Google Fonts and offline access

Google Fonts are loaded from Google's CDN over the internet, so if a user in a rural area of Malawi has no internet connection, the `<link>` request to fonts.googleapis.com will simply fail to load. The browser doesn't leave the text blank though — it falls back to the next font listed in the `font-family` stack. This is exactly why the lab always lists fallback fonts, e.g. `font-family: 'Poppins', Arial, sans-serif;`. If Poppins can't load, the browser tries Arial, and if that's unavailable too, it falls back to the operating system's generic sans-serif font. To make sure the page stays genuinely readable without internet, it's good practice to always include a common, pre-installed fallback font (like Arial or Georgia) at the end of every `font-family` list, rather than relying on the Google Font alone.

### 4. HSL — Hue, Saturation, Lightness

In `hsl(hue, saturation, lightness)`: **hue** is a position on the colour wheel from 0–360° (0/360 = red, 120 = green, 240 = blue); **saturation** is how intense or "pure" the colour is, from 0% (grey, no colour) to 100% (fully vivid); and **lightness** controls how close the colour is to black or white, from 0% (black) through 50% (the pure colour) to 100% (white). For `hsl(120, 100%, 50%)`, which is a vivid pure green, making it "much lighter" means increasing the **lightness** value — pushing it up to somewhere around 80–90% would turn it into a soft, pale green while keeping the same hue and saturation.