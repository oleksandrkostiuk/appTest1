# What We Make — Test Cases
Feature: about
Scope: UI
Total: 3 cases (Critical: 0, High: 0, Medium: 0, Low: 3)

---

ID: TC-ABOUT-MAKE-001
Title: "What We Make" heading and copy are visible
Type: UI
Feature: about
Flow: what-we-make
Priority: Low
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected heading (h2): What We Make
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Read the heading and the paragraphs below it
Expected Result: The h2 "What We Make" is visible followed by one regular paragraph and one italic paragraph; no text is cut off.
Linked Requirement: None

---

ID: TC-ABOUT-MAKE-002
Title: CEO attribution is shown under the quote
Type: UI
Feature: about
Flow: what-we-make
Priority: Low
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected attribution: —Vipul Bhagat, President & CEO
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Find the quote at the end of the "What We Make" section
Expected Result: The quote is followed by the attribution "—Vipul Bhagat, President & CEO".
Linked Requirement: None

---

ID: TC-ABOUT-MAKE-003
Title: Section order: Design Leadership, What We Make, What Sets Us Apart
Type: UI
Feature: about
Flow: what-we-make
Priority: Low
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected order of h2: Who We Are, Design Leadership, What We Make, What Sets Us Apart?, Environmental Values
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. List all h2 headings in DOM order and compare with the visual order after scrolling
Expected Result: The five h2 headings appear in the listed order, both in the DOM and visually.
Linked Requirement: None

---
