# Environmental Values — Test Cases
Feature: about
Scope: UI
Total: 5 cases (Critical: 0, High: 0, Medium: 2, Low: 3)

---

ID: TC-ABOUT-ENV-001
Title: Five subsections are shown in the expected order
Type: UI
Feature: about
Flow: environmental-values
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected h3 order: Testing Data; Local Sourcing; No Acid, No Sand; Recycling for Reduced Impact; Eco-Friendly Packaging Solutions
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Read the h3 headings under the "Environmental Values" h2 in order
Expected Result: The h2 "Environmental Values" is followed by exactly these 5 h3 subsections in this order (note "No Acid, No Sand" is a single subsection). Only headings and order are asserted, not full copy.
Linked Requirement: None

---

ID: TC-ABOUT-ENV-002
Title: HPD document link opens the PDF
Type: UI
Feature: about
Flow: environmental-values
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected href: /wp-content/uploads/HPD_v2.3_SkylineDesign.pdf
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Click the HPD link in the Testing Data subsection
Expected Result: The PDF opens (HTTP 200, content type application/pdf) and is not an empty file or a 404 page.
Linked Requirement: None

---

ID: TC-ABOUT-ENV-003
Title: In-text links have the expected hrefs
Type: UI
Feature: about
Flow: environmental-values
Priority: Low
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Resources=/resources/; Vitracolor=/vitracolor/; Eco-etch=/techniques/; Sustainability=/sustainability/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Read the href of the Resources, Vitracolor, Eco-etch and Sustainability links in the section
Expected Result: Each link href points to the path listed in Test Data.
Linked Requirement: None

---

ID: TC-ABOUT-ENV-004
Title: In-text links resolve without errors
Type: UI
Feature: about
Flow: environmental-values
Priority: Low
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Links: Resources, Vitracolor, Eco-etch, Sustainability
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Open each in-text link of the section one after another (request or click and go back)
Expected Result: Every target responds with a success status and renders a page (no 404/500). Content of the target pages is not asserted.
Linked Requirement: None

---

ID: TC-ABOUT-ENV-005
Title: Section image loads
Type: UI
Feature: about
Flow: environmental-values
Priority: Low
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Image: picture in the Environmental Values section
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Scroll slowly from top to bottom so every section is revealed (some sections are hidden until scrolled into view)
  3. Check the section image (complete = true, naturalWidth > 0)
Expected Result: The image is displayed with real dimensions; no broken-image icon.
Linked Requirement: None

---
