# Phase 4: Testing, Validation & Security

The objective of this phase is to ensure the solution works as expected, meets all functional requirements, and follows basic security and access-control best practices.

It validates the end-to-end automation, confirms data accuracy, and ensures only authorized users can access or modify ticket data.

## Data Validation Checks
- Mandatory fields are captured correctly.
- Auto-number is generated without duplication.
- Category and Subcategory values are stored accurately.
- Reference fields resolve correctly to the user and group tables.

## Activity 1: Testing & Validation (Test Scenario 1)
- Enter a Caller Name.
- Short Description: `WiFi not working in library`
- Save the form and reload it.
- Expected result (auto-filled):
  - Category → **Network**
  - Subcategory → **WiFi**
  - Email sent to the caller's email ID.

## Activity 2: Check Email Notification
1. Open All menus → search **Emails**.
2. Under System Logs → select **Emails**.
3. Search with the given subject name.
4. Open that record and, under Related Links, click **Preview mail**.

## Activity 3: Test Scenario 2
- Enter a Caller Name.
- Short Description: `Projector not turning on`
- Save the form and reload it.
- Expected result (auto-filled):
  - Category → **Hardware**
  - Subcategory → **Projector**
  - Email sent to the caller's mail ID.
