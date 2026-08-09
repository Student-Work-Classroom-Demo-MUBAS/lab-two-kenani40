# Lab 2  Reflection

**Student Name:** Mphatso Kenani
**Student ID:** BECE/21/SS/009

---

### 1. Selector conflict  `p { color: red }` vs `.intro { color: blue }`

The text will be blue. A class selector beats an element selector, no matter which rule is written first. according to my research CSS specificity is  element < class < ID, and the most specific match wins. If both rules were the same type (both element or both class), then whichever came last in the file would win instead.

### 2. `rem` units and accessibility

`rem` means "root em" : sized relative to the root `<html>` font-size (default 16px), not a fixed pixel value. If a user alters their browser's default font size to 20px, anything in `rem` grows with it, so the page stays readable. `px` would ignore that setting completely and stays locked at the same size. So a `1rem` paragraph would become 20px, while a `16px` paragraph stays exactly 16px.

### 3. Google Fonts and offline access

Google Fonts load from Google's servers, so with no internet the font request just fails. The browser doesn't leave blank text — it falls back to the next font in the `font-family` list, e.g. `'Poppins', Arial, sans-serif`.This explains the reason why fallbacks matter: we should always end the list with a common, pre-installed font like Arial or Georgia so the page stays readable offline instead of depending on the Google Font alone.

### 4. HSL — Hue, Saturation, Lightness

Hue is the colour itself, 0–360° on the colour wheel (0=red, 120=green, 240=blue). Saturation is how strong the colour is, 0% (grey) to 100% (vivid). Lightness is how close to black or white it is, 0% (black) to 100% (white), with 50% being the pure colour. To make `hsl(120, 100%, 50%)` much lighter, raise the lightness — around 80–90% turns it into a soft pale green, same hue and saturation.