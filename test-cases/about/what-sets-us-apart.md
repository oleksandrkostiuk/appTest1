# What Sets Us Apart — Test Cases
Feature: about
Scope: UI
Total: 4 cases (Critical: 0, High: 0, Medium: 4, Low: 0)

---

ID: TC-ABOUT-APART-001
Title: Heading and exactly two cards are displayed
Type: UI
Feature: about
Flow: what-sets-us-apart
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected heading (h2): What Sets Us Apart? ; cards: One Stop Shop, Make It Easy
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Look at the "What Sets Us Apart?" section
Expected Result: The h2 "What Sets Us Apart?" is visible with exactly 2 cards: "One Stop Shop" and "Make It Easy".
Linked Requirement: None

---

ID: TC-ABOUT-APART-002
Title: "One Stop Shop" card has image, heading and text
Type: UI
Feature: about
Flow: what-sets-us-apart
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Card: One Stop Shop
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Inspect the "One Stop Shop" card
Expected Result: The card contains an image, an h3 "One Stop Shop" and a non-empty text block.
Linked Requirement: None

---

ID: TC-ABOUT-APART-003
Title: "Make It Easy" card has image, heading and text
Type: UI
Feature: about
Flow: what-sets-us-apart
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Card: Make It Easy
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Inspect the "Make It Easy" card
Expected Result: The card contains an image, an h3 "Make It Easy" and a non-empty text block.
Linked Requirement: None

---

ID: TC-ABOUT-APART-004
Title: Card images load
Type: UI
Feature: about
Flow: what-sets-us-apart
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Images: the 2 card images
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Check each card image (complete = true, naturalWidth > 0)
Expected Result: Both card images are displayed with real dimensions; no broken-image icons.
Linked Requirement: None

---
