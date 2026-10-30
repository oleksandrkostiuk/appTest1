# Who We Are Content — Test Cases
Feature: about
Scope: UI
Total: 4 cases (Critical: 0, High: 0, Medium: 4, Low: 0)

---

ID: TC-ABOUT-WHOWE-001
Title: "Who We Are" section heading is visible
Type: UI
Feature: about
Flow: who-we-are-content
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected heading (h2): Who We Are
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the section below the hero
Expected Result: An h2 "Who We Are" is visible and sits directly below the hero.
Linked Requirement: None

---

ID: TC-ABOUT-WHOWE-002
Title: Intro copy contains the key company facts
Type: UI
Feature: about
Flow: who-we-are-content
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Key phrases: Charlie Rizzo, 1983, Chicago, 40 years
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Read the text of the three paragraphs in the "Who We Are" section
Expected Result: The section has 3 paragraphs, in order, and together they mention founder Charlie Rizzo, the year 1983, Chicago and 40+ years. Full wording is not asserted.
Linked Requirement: None

---

ID: TC-ABOUT-WHOWE-003
Title: Section image loads
Type: UI
Feature: about
Flow: who-we-are-content
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Image: the picture next to the "Who We Are" copy
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the "Who We Are" section
  3. Check the section image (naturalWidth > 0, complete = true)
Expected Result: The image is displayed with real dimensions; no broken-image icon.
Linked Requirement: None

---

ID: TC-ABOUT-WHOWE-004
Title: History link is present and resolves
Type: UI
Feature: about
Flow: who-we-are-content
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Link text: History (currently https://skyline.glass/history/ — production domain)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Find the "History" link in the "Who We Are" text
  3. Click it (or request its href)
Expected Result: The link is present and its target responds with a success status (not 404/500) and shows a page. The domain (dev vs production) is not asserted; a dev-to-prod link is reported as a note.
Linked Requirement: None

---
