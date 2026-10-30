# Mobile Menu — Test Cases
Feature: about
Scope: UI
Total: 7 cases (Critical: 1, High: 3, Medium: 2, Low: 1)

---

ID: TC-ABOUT-MMENU-001
Title: Hamburger is shown and desktop nav is hidden on mobile
Type: UI
Feature: about
Flow: mobile-menu
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 375x812; control: #menu-burger-opener
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Look at the header
Expected Result: The header shows the logo, a search icon and a hamburger icon. The desktop nav links are not displayed.
Linked Requirement: None

---

ID: TC-ABOUT-MMENU-002
Title: Hamburger opens the menu with all expected items
Type: UI
Feature: about
Flow: mobile-menu
Priority: Critical
Tags: smoke, regression
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected items: Products, Portfolio, Resources, About, Contact, Get a Quote, Get a Sample
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Tap the hamburger icon
  3. Read the items of the opened menu
Expected Result: The menu opens and lists Products, Portfolio, Resources, About, Contact, Get a Quote and Get a Sample.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-MMENU-003
Title: Menu opening slides the page and shows the menu panel
Type: UI
Feature: about
Flow: mobile-menu
Priority: Low
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: page content slides left; dark-blue menu panel
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Tap the hamburger icon
  3. Observe the page content and the menu panel
Expected Result: The page content slides to the left and a dark-blue menu panel is shown; no content overlaps the menu items.
Linked Requirement: None

---

ID: TC-ABOUT-MMENU-004
Title: Menu item navigates to the correct page
Type: UI
Feature: about
Flow: mobile-menu
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Item: Contact -> /contact/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Tap the hamburger icon
  3. Tap "Contact"
Expected Result: URL becomes /contact/ and the Contact page loads (HTTP 200, no error page).
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-MMENU-005
Title: Menu can be closed and the page returns to normal
Type: UI
Feature: about
Flow: mobile-menu
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Close control: hamburger icon (or close icon if shown)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Tap the hamburger icon to open the menu
  3. Tap the same control again (or the close icon)
Expected Result: The menu closes, the page content slides back, and the /about/ page is fully visible and scrollable.
Linked Requirement: None

---

ID: TC-ABOUT-MMENU-006
Title: Search icon is available next to the hamburger on mobile
Type: UI
Feature: about
Flow: mobile-menu
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Mobile viewport 375x812
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Control: search icon in the mobile header
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Tap the search icon in the header
Expected Result: A search input becomes visible; it can be closed again without leaving the page.
Linked Requirement: None

---

ID: TC-ABOUT-MMENU-007
Title: Hamburger is not shown on desktop
Type: UI
Feature: about
Flow: mobile-menu
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Viewport: 1536x864
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Look at the header and check whether #menu-burger-opener is displayed
Expected Result: The hamburger is not displayed; the full desktop nav is shown instead.
Linked Requirement: None

---
