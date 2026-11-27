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
- Head: Added Google Fonts Montserrat as default font-sans in weigths 400 600 700. Added color-brand: #2B1B12 as default font color.
- Header: Nav expands to a horizontal band on lg. On phone and md it is replaced by a 3-bar-icon which expands vertically upon click and hovers above the rest of the site. This panel is using color-cream: #FEF7F2. The Figma template shows a sign-up button and icons for search and a user account. These have been omitted as the site currently will not include this functionality.
- **Colours:** Use the theme classes, not hex codes (`bg-[#…]`, `text-[#…]`), for any colour that exists in the theme. `text-brand` for headings, nav and buttons (`bg-brand` on buttons). `text-cocoa` for body text. `text-taupe` for field labels, but never on `bg-sand`, because the contrast is too low. `bg-sand` for cards, the search bar and the footer band. `bg-cream` for the hero, testimonials and inputs. All five are defined in the `@theme` block in the `<head>` of `index.html`.
- Head (hero): Added Montserrat weight 800 (ExtraBold) to the Google Fonts link, used for the hero headline.
- Hero: Text and image side by side on lg, stacked on phone. The search bar overlaps the lower edge of the image on lg (`lg:-mt-24`). The text column has `lg:pb-32`, which is that 96px overlap plus 32px of space above the bar, so the two values must be changed together. The search bar uses the full content width on lg, so "Price Range" fits at 1024px. The header and the hero use `bg-cream`.
- Padding exception: On lg the hero image extends to the right edge of the screen (`lg:w-[calc(100%+6.5rem)]`, where 6.5rem is the lg side padding). The hero section has `overflow-x-clip` so the page doesn't scroll sideways. If the lg side padding changes, change this value too.