# Design Leadership — Test Cases
Feature: about
Scope: UI
Total: 5 cases (Critical: 0, High: 1, Medium: 4, Low: 0)

---

ID: TC-ABOUT-LEAD-001
Title: "Design Leadership" heading is visible after scrolling
Type: UI
Feature: about
Flow: design-leadership
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected heading (h2): Design Leadership
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
Expected Result: An h2 "Design Leadership" is visible when the section is scrolled into view.
Linked Requirement: None

---

ID: TC-ABOUT-LEAD-002
Title: Section content is hidden until scrolled into view and then revealed
Type: UI
Feature: about
Flow: design-leadership
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Initial state: visibility hidden; after scroll: visible
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Without scrolling, inspect the Design Leadership content (visibility / opacity)
  3. Scroll the section into the viewport
  4. Inspect the content again
Expected Result: Before scroll the content is not visible; after scrolling the section into view the heading and portraits become visible and remain visible when scrolling away and back.
Linked Requirement: None

---

ID: TC-ABOUT-LEAD-003
Title: Five portraits are displayed and load
Type: UI
Feature: about
Flow: design-leadership
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected portraits: 5
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Count the portrait images in the Design Leadership carousel
  4. Check each image loaded (naturalWidth > 0)
Expected Result: Exactly 5 portraits are present and each renders as an image (no broken-image icon).
Linked Requirement: None

---

ID: TC-ABOUT-LEAD-004
Title: Carousel can be moved horizontally to show all portraits
Type: UI
Feature: about
Flow: design-leadership
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Carousel: horizontal, 5 items
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Scroll or drag the carousel horizontally to the last item, then back to the first
Expected Result: All 5 portraits can be reached and viewed; the carousel does not get stuck and does not cause page-level horizontal scroll.
Linked Requirement: None

---

ID: TC-ABOUT-LEAD-005
Title: [a11y] Portraits have non-empty alt text
Type: UI
Feature: about
Flow: design-leadership
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: alt attribute non-empty on all 5 portrait images (currently alt="" on all 5)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Read the alt attribute of each portrait image
Expected Result: Every portrait has a non-empty, meaningful alt text (for example the person's name). Intended names/titles are an open question, so only non-empty alt is asserted.
Linked Requirement: None

---
