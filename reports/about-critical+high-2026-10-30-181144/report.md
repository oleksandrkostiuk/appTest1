# Test Report — about-critical+high · 2026-10-30 18:11

| Field | Value |
|---|---|
| Run ID | about-critical+high-2026-10-30-181144 |
| Environment | dev — https://dev.skyline.glass/ |
| Selection | feature=about priority=Critical+High (21 cases) |
| Model | claude-sonnet-5-5 |

## Summary

| Total | Pass | Fail | Blocked | Flaky | Pass rate |
|---|---|---|---|---|---|
| 21 | 18 | 3 | 0 | 0 | 85.7% |

Pass rate = Pass / Total. Flaky and Blocked are not counted as pass.

## Results by Priority

| Priority | Total | Pass | Fail | Blocked | Flaky |
|---|---|---|---|---|---|
| Critical | 4 | 4 | 0 | 0 | 0 |
| High | 17 | 14 | 3 | 0 | 0 |
| Medium | 0 | 0 | 0 | 0 | 0 |
| Low | 0 | 0 | 0 | 0 | 0 |

## Results by Flow

| Flow | Total | Pass | Fail | Blocked | Flaky |
|---|---|---|---|---|---|
| about/accessibility-basics | 1 | 0 | 1 | 0 | 0 |
| about/cta-and-footer-contact | 2 | 1 | 1 | 0 | 0 |
| about/design-leadership | 1 | 1 | 0 | 0 | 0 |
| about/header-navigation-desktop | 6 | 6 | 0 | 0 | 0 |
| about/mobile-menu | 4 | 4 | 0 | 0 | 0 |
| about/page-metadata-and-hero | 4 | 3 | 1 | 0 | 0 |
| about/responsive-layout | 3 | 3 | 0 | 0 | 0 |

## Failed (3)

| ID | Priority | Title | Expected | Actual | Evidence |
|---|---|---|---|---|---|
| TC-ABOUT-A11Y-006 | High | [a11y] Hamburger can be focused and operated with the keyboard | The hamburger is reachable with Tab, shows a visible focus indicator, and opens/closes the menu with Enter and Space (currently it is a <span> without tabindex or role). | At 375x812 the hamburger is a <span class="menu-burger"> with no tabindex, role or aria-label. Tab order went skip-link -> logo -> body content links; the hamburger never received focus (also not within 40 Tab presses on retry), so Enter/Space could not be tested on it. Error: Hamburger not keyboard focusable: document.activeElement never equals .menu-burger | screenshots/TC-ABOUT-A11Y-006.png |
| TC-ABOUT-CTA-008 | High | All social links use HTTPS | All four hrefs start with https://. An http:// link is a defect (the browser blocks it as Mixed Content). | Footer social hrefs: Instagram https://, LinkedIn https://, Facebook https://, YouTube http://www.youtube.com/@skyline-glass (not HTTPS). Same result on both attempts. Error: YouTube link uses http:// scheme | screenshots/TC-ABOUT-CTA-008.png |
| TC-ABOUT-META-003 | High | Page has a single non-empty H1 containing the hero text | Exactly one <h1> exists and its text is "Over 40 years of Chicago-made glass." (currently the h1 is empty and the hero text is in a <div> — confirmed defect). | Exactly one <h1> exists but it is empty (innerHTML is a single space); the hero text "Over 40 years of Chicago-made glass." is rendered in a <div class="font-bold type-42 ..."> instead. Reproduced on both attempts. Error: Assertion mismatch: h1 text is "" (expected "Over 40 years of Chicago-made glass.") | screenshots/TC-ABOUT-META-003.png |

## Flaky (0)

None

## Blocked (0)

None

## Needs decision (3)

- TC-ABOUT-A11Y-006 failed: the mobile hamburger is a span with no tabindex, role or aria-label and is never reachable by keyboard. Likely a product accessibility defect; confirm and file a bug.
- TC-ABOUT-CTA-008 failed: the footer YouTube link uses http://www.youtube.com/@skyline-glass, not HTTPS. Likely a product defect (content/config); confirm and file a bug.
- TC-ABOUT-META-003 failed: the page has one empty <h1> and the hero text sits in a styled <div>. Likely an SEO/accessibility defect; confirm and file a bug.

## Notes (0)

None

<details>
<summary>Passed (18)</summary>

| ID | Title |
|---|---|
| TC-ABOUT-CTA-002 | CTA Contact button opens the Contact page |
| TC-ABOUT-LEAD-003 | Five portraits are displayed and load |
| TC-ABOUT-NAVD-001 | Header shows logo, all 7 nav links in order and search icon |
| TC-ABOUT-NAVD-002 | Nav link hrefs point to the correct pages |
| TC-ABOUT-NAVD-003 | Logo links to the home page |
| TC-ABOUT-NAVD-005 | Contact link opens the Contact page |
| TC-ABOUT-NAVD-006 | Get a Quote link opens the quote request page |
| TC-ABOUT-NAVD-007 | Get a Sample link opens the sample request page |
| TC-ABOUT-MMENU-001 | Hamburger is shown and desktop nav is hidden on mobile |
| TC-ABOUT-MMENU-002 | Hamburger opens the menu with all expected items |
| TC-ABOUT-MMENU-004 | Menu item navigates to the correct page |
| TC-ABOUT-MMENU-005 | Menu can be closed and the page returns to normal |
| TC-ABOUT-META-001 | Page title is "About Skyline Design" |
| TC-ABOUT-META-002 | Hero heading text is visible on load |
| TC-ABOUT-META-004 | Meta description is present and not empty |
| TC-ABOUT-RESP-001 | No horizontal overflow on desktop (1536px) |
| TC-ABOUT-RESP-002 | No horizontal overflow on tablet (768px) |
| TC-ABOUT-RESP-003 | No horizontal overflow on mobile (375px) |

</details>
