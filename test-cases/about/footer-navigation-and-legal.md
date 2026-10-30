# Footer Navigation and Legal — Test Cases
Feature: about
Scope: UI
Total: 6 cases (Critical: 0, High: 0, Medium: 5, Low: 1)

---

ID: TC-ABOUT-FOOT-001
Title: Footer shows all 15 navigation links
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected links: Home, Products, Collections, Patterns, Projects, About, History, Sustainability, Design Partners, News, Request a Sample, Request a Quote, Careers, Resources, Contact
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the labels of the footer navigation links
Expected Result: Exactly the 15 links listed in Test Data are shown (the footer label is "Projects" while the header label is "Portfolio").
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-FOOT-002
Title: Footer nav link hrefs point to the correct pages
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Home=/; Products=/products/; Collections=/collections/; Patterns=/patterns/; Projects=/projects/; About=/about/; History=/history/; Sustainability=/sustainability/; Design Partners=/design-partners/; News=/news/; Request a Sample=/sample-request/; Request a Quote=/quote-request/; Careers=/careers/; Resources=/resources/; Contact=/contact/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the href of each footer navigation link
Expected Result: Each href equals the path in Test Data on the dev host.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-FOOT-003
Title: Footer nav links resolve without errors
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Links: the 15 footer navigation links
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Request or open each footer navigation link
Expected Result: Every link returns a success status and renders a page (no 404/500). Content of the target pages is not asserted.
Linked Requirement: None

---

ID: TC-ABOUT-FOOT-004
Title: Footer copyright line shows the current year range
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Low
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected pattern: Skyline Design © 2020-<current year> | All Rights Reserved.
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the copyright line
Expected Result: The line matches "Skyline Design © 2020-<current year> | All Rights Reserved." where the end year equals the current year. The year is not hard-coded.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-FOOT-005
Title: Privacy Policy link opens the Privacy Policy page
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /privacy-policy/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Click "Privacy Policy"
Expected Result: URL becomes /privacy-policy/ and the page loads (HTTP 200, no error page).
Linked Requirement: None

---

ID: TC-ABOUT-FOOT-006
Title: Terms & Conditions link opens the Terms page
Type: UI
Feature: about
Flow: footer-navigation-and-legal
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /terms-conditions/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Click "Terms & Conditions"
Expected Result: URL becomes /terms-conditions/ and the page loads (HTTP 200, no error page).
Linked Requirement: None

---
