---
marp: true
---

<!-- headingDivider: 4 -->

# Accessibility Crash Course

## Things to Avoid

### Don't Use Semantic Elements For Styling

#### `link` vs. `pushbutton` vs. `div`

-  `<a href="">` (`role="link"`)
    - has a target URL
    - cannot be disabled
-  `<button>` (`role="pushbutton"`)
    - does not change `window.location` (except maybe parameters)
    - can be disabled
- `div` / `span` / ... (no `role` )
    - non-interactive
    - appropriate as a "disabled link"
- `class="clickable"`
    - avoid

#### Headings

- one `h1` on each page
- increase only by one
- don't use for style
- don't use as label or for grouping form elements

## Aria

- used to change semantics of HTML elements to something *else*
- avoid if possible

### `aria-label`
- substitutes `<label for="">`
- only for interactive elements
- can cause unexpected behavior when not used properly
    - `listbox` `option`

## Things to Look Out For

### Is the Component Usable Via Keyboard?

- Can all interactive elements be reached via <kbd>Tab</kbd>?
- Does the order make sense?
- Can the user control all interactive elements via keyboard?

### Are Interactive Elements Correctly Labelled?

- Check the accessibility name of focusable elements with the "Accessibility" tab in dev tools
- Heading vs. `fieldset` / `group` vs. `label`

### Do Non-textual Elements Have Textual alternatives?

- E.g.
    - Images
        - Often `alt=""` is appropriate
    - Icons
    - Color pickers
- Non-interactive:
    - Use visually hidden `span`s for non-focusable elements
    - Hide possible bogus content with `aria-hidden`
- Interactive:
    - Label the interactive elements directly