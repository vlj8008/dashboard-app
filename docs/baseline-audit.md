# Baseline Audit

Date: 2026-09-22
URL: http://localhost:5173/
Scope: Dashboard, Invoices, Projects, Analytics, Customers, Data Sources, Settings

## Summary

All seven requested sidebar items were located and clicked sequentially. The app stayed on the same dashboard view for every item. The links are anchors with `href="#"`, so they are inert mockups rather than working navigation routes.

No console errors were emitted during the click sequence.

## Results

| Menu item | URL result | View result | Operational status | Console errors |
| --- | --- | --- | --- | --- |
| Dashboard | Changed from `http://localhost:5173/` to `http://localhost:5173/#` | Dashboard remained unchanged | Inert hash link; dashboard is already the current view | None |
| Invoices | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |
| Projects | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |
| Analytics | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |
| Customers | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |
| Data Sources | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |
| Settings | Remained `http://localhost:5173/#` | Dashboard remained unchanged | Dead link / mockup | None |

## Evidence

- Sidebar inspection found seven anchors matching the requested labels.
- Every inspected anchor had `href="#"`.
- The dashboard main-content text was unchanged before and after each click.
- No console `error` events occurred after any click.
- The page's active styling remained on Dashboard; the other six links did not become active.

## Execution Note

The shared browser page was not visible to normal Playwright click actionability checks, so the same real locators were clicked with `force: true`. This bypassed only the visibility check; URL, DOM view, active-class, and console-event assertions were still collected from the page.

## Create Invoice Button Findings

The dashboard's `Create Invoice` button was tested in the earlier baseline walkthrough.

| Check | Finding | Status |
| --- | --- | --- |
| Open modal | Clicking `Create Invoice` opened the `Create New Invoice` modal. | Working |
| Enter title | The form has a `Client Name` field rather than a field labeled `Title`; entering `Baseline Verification` succeeded. | Working with label mismatch |
| Enter amount | Entering `1500` into `Amount ($)` succeeded. | Working |
| Submit form | Clicking `Save Invoice` closed the modal without a UI error. | Working |
| New table row | A new `INV-006` row appeared with `Baseline Verification`, `$1,500.00`, and `Pending`. | Working |
| Status filtering | No pending/paid filter control exists in the current dashboard, so interactive filtering could not be performed. | Not implemented |

The invoice creation flow emitted no console errors during the recorded interaction. The app did emit failed network requests to the placeholder Supabase URL while loading, but the local fallback data and invoice creation flow still rendered and worked.