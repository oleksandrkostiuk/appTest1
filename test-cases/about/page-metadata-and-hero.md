# Page Metadata and Hero — Test Cases
Feature: about
Scope: UI
Total: 7 cases (Critical: 2, High: 2, Medium: 2, Low: 1)

---

ID: TC-ABOUT-META-001
Title: Page title is "About Skyline Design"
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: Critical
Tags: smoke, regression
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected title: About Skyline Design
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Read the browser tab / document title
Expected Result: Document title is exactly "About Skyline Design".
Linked Requirement: None

---

ID: TC-ABOUT-META-002
Title: Hero heading text is visible on load
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: Critical
Tags: smoke, regression
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Hero text: Over 40 years of Chicago-made glass.
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Look at the hero block at the top of the page
Expected Result: The hero text "Over 40 years of Chicago-made glass." is visible, fully opaque and not clipped or overlapped by the header.
Linked Requirement: None

---

ID: TC-ABOUT-META-003
Title: Page has a single non-empty H1 containing the hero text
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: High
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected H1: Over 40 years of Chicago-made glass.
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Inspect the page headings and count elements with tag h1
  3. Read the text content of the h1
Expected Result: Exactly one <h1> exists and its text is "Over 40 years of Chicago-made glass." (currently the h1 is empty and the hero text is in a <div> — confirmed defect).
Linked Requirement: None

---

ID: TC-ABOUT-META-004
Title: Meta description is present and not empty
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: High
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Selector: meta[name="description"]
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Read the content attribute of meta[name="description"] in the page head
Expected Result: A meta description tag exists and its content is a non-empty, human-readable sentence (not a placeholder such as "Just another WordPress site").
Linked Requirement: None

---

ID: TC-ABOUT-META-005
Title: Canonical URL points to the dev /about/ page
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: Medium
Tags: smoke
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Expected canonical: https://dev.skyline.glass/about/
Steps:
  1. Open /about/ on the dev environment and wait for the page to finish loading (about 3 seconds, so hero animation completes)
  2. Read the href of link[rel="canonical"] in the page head
Expected Result: Canonical link equals https://dev.skyline.glass/about/ (no query string, includes trailing slash).
Linked Requirement: None

---

ID: TC-ABOUT-META-006
Title: Hero text reaches full opacity after the load animation
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: Low
Tags: boundary
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Wait times: immediately after load, then 3 seconds later
Steps:
  1. Navigate to /about/ and immediately observe the hero text
  2. Wait 3 seconds and observe the hero text again
Expected Result: Hero text may be faint right after load, but after about 2-3 seconds it is fully opaque (computed opacity 1) and stays visible.
Linked Requirement: None

---

ID: TC-ABOUT-META-007
Title: Page loads without console errors
Type: UI
Feature: about
Flow: page-metadata-and-hero
Priority: Medium
Tags: negative
Preconditions:
  - Anonymous user (not logged in)
  - Desktop viewport 1536x864
  - Environment: dev (base URL from PROJECT_CONFIG.json)
Test Data: Console level: error (warnings are allowed)
Steps:
  1. Open the browser console, then navigate to /about/ and wait for load
  2. Review console entries of level "error"
Expected Result: Page returns HTTP 200 and the console contains 0 errors on initial load. Known warnings (GSAP "target not found", manifest start_url, deprecated apple-mobile-web-app-capable meta) are not failures.
Linked Requirement: None

---
