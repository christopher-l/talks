% Accessibility: Lessons Learned
% Christopher Lübbemeier

<style type="text/css">
  .reveal p {
    text-align: left;
  }
  .reveal ul {
    display: block;
  }
  .reveal ol {
    display: block;
  }
</style>

# Things to Avoid

## Don't Use Semantic Elements For Styling

## `link` Vs. `pushbutton` Vs. `div`

- `<a href="">` (`role="link"`)
    - Has a target URL
    - Cannot be disabled
- `<button>` (`role="pushbutton"`)
    - Does not change `window.location`  
        - Except maybe parameters
    - Can be disabled
- `div` / `span` / ... (no `role` )
    - Non-interactive
    - Appropriate as a "disabled link"

---

`class="clickable"`

- Avoid

## Headings

- One `h1` on each page
- Increase only by one
- Don't use for style
- Don't use as label or for grouping form elements

# Aria

## When (Not) to Use Aria

- Used to change semantics of HTML elements to something *else*
- Avoid if possible

## `aria-label`

- Substitutes `<label for="">`
- Only for interactive elements
- Can cause unexpected behavior when not used properly
    - `listbox` `option`


# How To Improve Things

## Things to Look Out For

---

Is the component usable via keyboard?

- Can all interactive elements be reached via <kbd>Tab</kbd>?
- Does the order make sense?
- Can the user control all interactive elements via keyboard?

---

Are interactive elements correctly labelled?

- Check the accessibility name of focusable elements with the "Accessibility" tab in dev tools
- Heading vs. `fieldset` / `group` vs. `label`

---

Do non-textual elements have textual alternatives?

- Images
    - Often `alt=""` is appropriate
- Icons
- Color pickers

---

Non-interactive:

- Use visually hidden `span`s for non-focusable elements
- Hide possible bogus content with `aria-hidden`

Interactive:

- Label the interactive elements directly

# Thank You