# CTA and Footer Contact — Test Cases
Feature: about
Scope: UI
Total: 8 cases (Critical: 0, High: 2, Medium: 6, Low: 0)

---

ID: TC-ABOUT-CTA-001
Title: CTA band shows headline and Contact button
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected headline: Transforming glass since 1983. ; button: Contact
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the call-to-action band above the footer
Expected Result: The band shows "Transforming glass since 1983." and a visible "Contact" button.
Linked Requirement: None

---

ID: TC-ABOUT-CTA-002
Title: CTA Contact button opens the Contact page
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected destination: /contact (no trailing slash in href; final URL may redirect to /contact/)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the CTA band
  3. Click the "Contact" button
Expected Result: The Contact page loads (HTTP 200, no error page). Either /contact or /contact/ is accepted as the final URL.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-CTA-003
Title: Footer shows the company address
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected address: Skyline 1240 N Homan Ave Chicago, IL 60651
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the address block
Expected Result: The footer address reads "Skyline 1240 N Homan Ave Chicago, IL 60651".
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-CTA-004
Title: Footer email is a working mailto link
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: sales@skyline.glass
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the email text and the href of the link
Expected Result: The text is "sales@skyline.glass" and the link href is mailto:sales@skyline.glass.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-CTA-005
Title: Footer phone number shows the live value and is a tel link
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: 773-278-4660 (the Jul 2025 checklist value 773-825-6203 is considered stale)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the phone text and the href of the link
Expected Result: The phone text is "773-278-4660" and the link href is a tel: link with the same number.
Linked Requirement: https://elekshelp.atlassian.net/wiki/spaces/SKLN/pages/4199710724

---

ID: TC-ABOUT-CTA-006
Title: Four social links are present and open safely in a new tab
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: security
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected: Instagram, LinkedIn, Facebook, YouTube; target=_blank; rel includes noopener
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read href, target and rel of the four social links
Expected Result: There are exactly 4 social links (Instagram, LinkedIn, Facebook, YouTube), each with target="_blank" and rel containing "noopener". Only attributes are asserted, never the content of the social pages (they block automation).
Linked Requirement: None

---

ID: TC-ABOUT-CTA-007
Title: Clicking a social link opens a new tab and keeps the About page
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Link: Instagram (any social link may be used)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Click the Instagram social icon
Expected Result: A new tab/window opens for the social URL and the original tab still shows /about/. Content of the social page is not asserted.
Linked Requirement: None

---

ID: TC-ABOUT-CTA-008
Title: All social links use HTTPS
Type: UI
Feature: about
Flow: cta-and-footer-contact
Priority: High
Tags: security, negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected scheme: https:// for Instagram, LinkedIn, Facebook, YouTube (currently YouTube is http://www.youtube.com/@skyline-glass)
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll to the footer
  3. Read the href of each social link and check its scheme
Expected Result: All four hrefs start with https://. An http:// link is a defect (the browser blocks it as Mixed Content).
Linked Requirement: None

---
