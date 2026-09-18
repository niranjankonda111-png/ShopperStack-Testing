# BUG-002: Expired coupon code is accepted and discount is applied incorrectly

**Module:** Cart / Checkout
**Reported By:** Niranjan Konda
**Status:** Open
**Priority:** High
**Severity:** High

## Steps to Reproduce
1. Add items worth more than the minimum order value to the cart
2. Go to the Cart page's coupon field
3. Enter a coupon code known to be expired (e.g., "EXPIRED99")
4. Click "Apply"

## Expected Result
System should reject the coupon and display an error message: "Invalid or expired coupon."

## Actual Result
The coupon is accepted, a 10% discount is applied to the cart total, and no validation error is shown.

## Environment
- Browser: Chrome (Latest)
- Module: Cart
- Test Data: Coupon code EXPIRED99 (expiry date in the past)

## Notes
Suggests the coupon validation logic may only be checking the code string against a valid-codes list, without checking the expiry date field. Recommend adding a date-based validation check server-side, since client-side-only validation could also be bypassed.
