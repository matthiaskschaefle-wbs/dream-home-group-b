# PLAN

## What we're building

We are building Dwello, a one-page real estate website for people looking for their next home.
It is based on the Find Your Dream Home Figma template, built with semantic HTML and Tailwind CSS, and published on GitHub Pages.

We will build all eight sections of the page, responsive from phone to desktop.
We will leave out anything that needs JavaScript or a backend: the search bar and the contact form are real form elements, but they don't send data anywhere.

## Who's in the group

- Matthias — 247690463+matthiaskschaefle@users.noreply.github.com
- Sebastian — 20282410+sebastianthimm@users.noreply.github.com
- Gajender — 182087728+Selgajen@users.noreply.github.com

## The split

- T1 Header & Navigation — Sebastian
- T2 Hero + Search — Sebastian
- T3 We Help You Find — Gajender
- T4 Why Choose Us — Gajender
- T5 Property Cards — Matthias
- T6 Testimonials — Matthias
- T7 Get-Help Form — Matthias
- T8 Footer — Sebastian

## Section ids

| Task | Section | id | Owner |
| --- | --- | --- | --- |
| T2 | Hero + Search | `home` | Sebastian |
| T3 | We Help You Find | `about` | Gajender |
| T4 | Why Choose Us | `features` | Gajender |
| T5 | Property Cards | `properties` | Matthias |
| T6 | Testimonials | `testimonials` | Matthias |
| T7 | Get-Help Form | `contact` | Matthias |

The header links (T1) point to these ids, so every section must use exactly this id.

## Decisions

- Mobile-first: we write the phone layout with plain utility classes first, then add `md:` and `lg:` on top.
- Breakpoints: we only use Tailwind's defaults, `md` and `lg`, so every section switches at the same width.
- Padding: To stay consistent across sections default side padding values should be px-6 md:px-10 lg:px-26.
- Done means: the section looks right on phone and desktop, uses semantic HTML, and one teammate approved the Pull Request.