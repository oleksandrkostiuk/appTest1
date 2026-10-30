# Header Navigation (Desktop) — Test Cases
Feature: about
Scope: UI
Total: 9 cases (Critical: 1, High: 5, Medium: 3, Low: 0)

---

ID: TC-ABOUT-NAVD-001
Title: Header shows logo, all 7 nav links in order and search icon
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: Critical
Tags: smoke, regression
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected nav order: Products, Portfolio, Resources, About, Contact, Get a Quote, Get a Sample
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Look at the header at the top of the page
  3. Read the nav labels left to right
Expected Result: Header shows the Skyline logo, the links Products, Portfolio, Resources, About, Contact, Get a Quote, Get a Sample in this order, and a search icon. No label is missing, truncated or wrapped onto a second line.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-002
Title: Nav link hrefs point to the correct pages
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Products=/products/; Portfolio=/projects/; Resources=/resources/; About=/about/; Contact=/contact/; Get a Quote=/quote-request/; Get a Sample=/sample-request/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Read the href attribute of each of the 7 header nav links
Expected Result: Each href resolves to the path listed in Test Data (same dev host). Note: the label is "Portfolio" while the URL is /projects/.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-003
Title: Logo links to the home page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: https://dev.skyline.glass/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click the Skyline logo in the header
Expected Result: Browser navigates to the home page (/) on the dev host; the home page renders without an error.
Linked Requirement: None

---

ID: TC-ABOUT-NAVD-004
Title: Products link opens the Products page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /products/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click "Products" in the header
Expected Result: URL becomes /products/ and the Products page loads (HTTP 200, no error page).
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-005
Title: Contact link opens the Contact page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /contact/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click "Contact" in the header
Expected Result: URL becomes /contact/ and the Contact page loads (HTTP 200, no error page).
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-006
Title: Get a Quote link opens the quote request page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /quote-request/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click "Get a Quote" in the header
Expected Result: URL becomes /quote-request/ and the quote request page loads (HTTP 200, no error page).
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-007
Title: Get a Sample link opens the sample request page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /sample-request/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click "Get a Sample" in the header
Expected Result: URL becomes /sample-request/ and the sample request page loads (HTTP 200, no error page).
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-NAVD-008
Title: About nav item is shown as the current page
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: Medium
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Current page: /about/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Compare the visual state of the "About" nav item with the other nav items (also check aria-current / active class)
Expected Result: The "About" item has a distinct active/current state (style, class or aria-current) that the other nav items do not have.
Linked Requirement: None

---

ID: TC-ABOUT-NAVD-009
Title: Search icon opens the search UI
Type: UI
Feature: about
Flow: header-navigation-desktop
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Control: search icon at the right end of the header
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Click the search icon in the header
Expected Result: A search input (field or overlay) becomes visible and receives focus; it can be closed again without leaving the page.
Linked Requirement: None

---
