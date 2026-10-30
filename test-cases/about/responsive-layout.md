# Responsive Layout — Test Cases
Feature: about
Scope: UI
Total: 8 cases (Critical: 0, High: 3, Medium: 5, Low: 0)

---

ID: TC-ABOUT-RESP-001
Title: No horizontal overflow on desktop (1536px)
Type: UI
Feature: about
Flow: responsive-layout
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 1536x864
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Compare document.documentElement.scrollWidth with the viewport width
Expected Result: scrollWidth does not exceed the viewport width; there is no horizontal scrollbar and no section is cut off.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-002
Title: No horizontal overflow on tablet (768px)
Type: UI
Feature: about
Flow: responsive-layout
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Tablet viewport 768x1024
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 768x1024
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Compare document.documentElement.scrollWidth with the viewport width
Expected Result: scrollWidth does not exceed the viewport width; there is no horizontal scrollbar and no section is cut off.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-003
Title: No horizontal overflow on mobile (375px)
Type: UI
Feature: about
Flow: responsive-layout
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 375x812
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Compare document.documentElement.scrollWidth with the viewport width
Expected Result: scrollWidth does not exceed the viewport width; there is no horizontal scrollbar and no section is cut off.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-004
Title: No horizontal overflow at the smallest common width (320px)
Type: UI
Feature: about
Flow: responsive-layout
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 320x568
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 320x568
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Compare document.documentElement.scrollWidth with the viewport width
Expected Result: scrollWidth does not exceed the viewport width; texts wrap and no content is cut off.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-005
Title: Section order is the same on desktop, tablet and mobile
Type: UI
Feature: about
Flow: responsive-layout
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected order: hero, Who We Are, Design Leadership, What We Make, What Sets Us Apart?, Environmental Values, CTA, footer
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Note the order of the sections
  4. Repeat at 768x1024 and 1536x864
Expected Result: Sections appear in the listed order at all three viewport widths; none is missing or duplicated.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-006
Title: Images are not broken at mobile width
Type: UI
Feature: about
Flow: responsive-layout
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 375x812
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Check every img element on the page (complete = true, naturalWidth > 0), including lazy-loaded ones
Expected Result: All visible images load; none overflows its container or is distorted beyond its aspect ratio.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-007
Title: Hero text is readable and not clipped on mobile
Type: UI
Feature: about
Flow: responsive-layout
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Hero text: Over 40 years of Chicago-made glass.
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Look at the hero block
Expected Result: The full hero text is visible, wrapped inside the viewport and not hidden behind the header.
Linked Requirement: None

---

ID: TC-ABOUT-RESP-008
Title: Layout switches when the window is resized from desktop to mobile
Type: UI
Feature: about
Flow: responsive-layout
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Resize: 1536x864 -> 375x812 without reloading
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Confirm the desktop nav links are visible
  3. Resize the window to 375x812 without reloading
  4. Look at the header and the page layout
Expected Result: The header switches to the mobile layout (search icon and hamburger instead of the nav links) and content reflows without horizontal overflow.
Linked Requirement: None

---
