# Accessibility Basics — Test Cases
Feature: about
Scope: UI
Total: 8 cases (Critical: 0, High: 1, Medium: 6, Low: 1)

---

ID: TC-ABOUT-A11Y-001
Title: [a11y] Heading hierarchy has one h1 and no skipped levels
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: 1 h1, then h2 sections, then h3 subsections
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. List all headings (h1-h6) in DOM order with their levels
Expected Result: There is exactly one h1, section headings are h2 and sub-headings are h3; no heading level is skipped.
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-002
Title: [a11y] No heading is empty
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Known empty headings: h1 (page), h3 under "Who We Are"
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. List all headings and read their text content
Expected Result: Every heading element has non-empty text (currently the h1 and one h3 under "Who We Are" are empty).
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-003
Title: [a11y] Content images have non-empty alt text
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Images: Who We Are image, 5 portraits, 2 card images, Environmental Values image
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Read the alt attribute of each content image
Expected Result: Every content image has a non-empty, descriptive alt. Purely decorative images may use alt="" but the 5 portraits are content images.
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-004
Title: [a11y] Social links have an accessible name with the network
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Links: Instagram, LinkedIn, Facebook, YouTube (currently all named "social profile - opens in a new tab")
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the accessible name of each social link (aria-label or image alt)
Expected Result: Each social link has a distinct accessible name that includes the network name, for example "Instagram - opens in a new tab".
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-005
Title: [a11y] All links have a non-empty accessible name
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Scope: all a elements on /about/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Collect every a element and compute its accessible name (text, aria-label, or image alt)
Expected Result: No link has an empty accessible name (including the logo link and the social links).
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-006
Title: [a11y] Hamburger can be focused and operated with the keyboard
Type: UI
Feature: about
Flow: accessibility-basics
Priority: High
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Keys: Tab, Enter, Space
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Press Tab until the hamburger receives focus
  3. Press Enter
  4. Close it, then repeat with Space
Expected Result: The hamburger is reachable with Tab, shows a visible focus indicator, and opens/closes the menu with Enter and Space (currently it is a <span> without tabindex or role).
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-007
Title: [a11y] Hamburger exposes role, label and expanded state
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Control: #menu-burger-opener
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Inspect #menu-burger-opener attributes
  3. Open the menu and inspect again
Expected Result: The control has an appropriate role (button), an accessible name (aria-label) and aria-expanded that changes between false and true.
Linked Requirement: None

---

ID: TC-ABOUT-A11Y-008
Title: [a11y] Header navigation follows a logical tab order with visible focus
Type: UI
Feature: about
Flow: accessibility-basics
Priority: Low
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Keys: Tab / Shift+Tab
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Press Tab repeatedly from the top of the page through the header
  3. Observe focus position and indicator at each stop
Expected Result: Focus moves through the logo and nav links left to right, a focus indicator is always visible, and there is no keyboard trap.
Linked Requirement: None

---
