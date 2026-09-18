# BUG-001: Cart total does not update when quantity is changed via keyboard input

**Module:** Cart
**Reported By:** Niranjan Konda
**Status:** Open
**Priority:** High
**Severity:** Medium

## Steps to Reproduce
1. Add any product to the cart
2. On the Cart page, click into the quantity input field
3. Manually type a new quantity (e.g., change 1 to 4) instead of using the +/- stepper buttons
4. Click outside the field (blur) without pressing Enter

## Expected Result
The item subtotal and cart total should recalculate automatically to reflect the new quantity (4x unit price).

## Actual Result
The quantity field visually shows "4", but the item subtotal and cart total still reflect the old quantity (1x unit price) until the page is refreshed.

## Environment
- Browser: Chrome (Latest)
- Module: Cart
- Test Data: Any single product, quantity changed via direct keyboard input

## Notes
Issue does not occur when using the +/- stepper buttons — only affects direct keyboard entry into the quantity field. Likely a missing "on blur" or "on change" event handler for the recalculation logic.
