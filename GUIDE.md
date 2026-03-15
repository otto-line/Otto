# OTTO — Design Studio Website Guide

Otto is a design studio website that showcases the studio's work. The interface is intentionally minimal — a sidebar of context on the left, and a render area on the right where project content loads in.

---

## Layout

The site uses a two-column CSS grid layout inside `.container`:

- **Left column (`.box`)** — Studio info, contact, and project list
- **Right column (`.render`)** — Project content loads here as an iframe

The `.box` uses a 3-row grid:
- Row 1: `.Bio` — Studio description
- Row 2: `.contact` — Email address
- Row 3: `.Projects` — Project list (pushed down with `margin-top`)

---

## Projects

Projects are stored in `projects.json`. Each project has:

```json
{
  "id": 1,
  "name": "Drum Magazine",
  "type": "Brand Design",
  "date": "2024-03-15",
  "client": "Drum Magazine",
  "createdBy": "Sam"
}
```

**Creators:** Sam, Ruby, Ottoline

**Types:** Websites, Brand Design, Book Design, Exhibitions, Posters

Each project will have its own `.html` file that renders inside the `.render` iframe on click.

---

## Typography

**Neue Haas Grotesk** (local `.otf` files) — used for all body text.

Available weights:
| Weight | File | Use |
|--------|------|-----|
| 100 | UltTh | Display only |
| 200 | Th | — |
| 300 | XLt | Years, captions |
| 400 | Lt | — |
| 500 | Rg | Body text |
| **600** | **Md** | **Default** |
| 700 | Bd | Headings |
| 900 | Blk | Display only |

**Mishafi Gold Regular** — available for decorative use.

Years in the project list are styled `font-weight: 300` + italic.

---

## Planned Features

### Interactivity
- [ ] Hover state on project list items — darker shade of grey
- [ ] Click to select a project item (highlight active state)
- [ ] Expandable list items on click — reveal more project detail inline
- [ ] Clicking a project loads its `.html` page into `.render` via iframe

### Theming
- [ ] Button to swap stylesheets — toggle between visual themes (e.g. dark/light, high contrast, serif/sans)
- [ ] Themes stored as separate `.css` files, swapped with JavaScript

### Mobile *(last step)*
- [ ] `.box` is hidden by default on mobile
- [ ] Hamburger icon appears in the header on small screens
- [ ] Tapping the hamburger slides/reveals `.box` as an overlay menu
- [ ] Tapping outside or closing the menu hides `.box` again
- [ ] `.render` takes full screen width on mobile

### Project Pages
- [ ] Each project gets its own `projects/project-name.html`
- [ ] Pages render inside `.render` iframe — no page navigation
- [ ] Consistent template: title, description, images, credits

---

## Suggested Ideas

- **Cursor follower** — a minimal dot or label that follows the cursor and shows the hovered project type
- **Filter by tag** — click a type (Websites, Posters, etc.) to filter the project list
- **Filter by creator** — show only Sam / Ruby / Ottoline's projects
- **Scroll to reveal** — project items fade or slide in on load, staggered
- **Monogram favicon** — use the OTTO logotype as a custom favicon
- **URL routing** — update the URL hash when a project is opened (`#drum-magazine`) so links are shareable
- **Project count** — small number next to "Projects" heading showing total
- **Transition on render load** — crossfade when a new project iframe loads

---

## File Structure

```
OTTO/
├── otto.html           # Main page
├── style.css           # Main stylesheet
├── projects.json       # Project data
├── GUIDE.md            # This file
├── NHaasGroteskDSPro-*.otf  # Font files (8 weights + italics)
└── projects/
    └── drum-magazine.html   # Individual project pages (to be created)
```
