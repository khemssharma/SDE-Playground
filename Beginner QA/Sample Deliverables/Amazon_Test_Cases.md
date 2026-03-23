# 📄 Sheet: Amazon Test Cases

| Test Case ID | Requirement ID | Module | Test Scenario | Preconditions | Test Steps | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC_001 | AMZ-LOGIN-001 | Login | Login with valid credentials | User account exists | 1. Click Sign In 2. Enter valid email 3. Enter valid password 4. Click Sign In | User redirected to homepage and logged in | High |
| TC_002 | AMZ-LOGIN-002 | Login | Login with invalid password | User account exists | 1. Enter valid email 2. Enter wrong password 3. Click Sign In | Error message displayed | High |
| TC_003 | AMZ-LOGIN-003 | Login | Login with empty fields | User on login page | 1. Leave email & password blank 2. Click Sign In | Validation message displayed | Medium |
| TC_004 | AMZ-LOGIN-004 | Login | Forgot password flow | User on login page | 1. Click Forgot Password 2. Enter email 3. Submit | Password reset link sent | Medium |
| TC_005 | AMZ-LOGIN-005 | Login | Logout functionality | User logged in | 1. Click Account 2. Click Sign Out | User logged out successfully | High |
| TC_006 | AMZ-SEARCH-001 | Search | Search product with valid keyword | User on homepage | 1. Enter 'Laptop' 2. Click Search | Relevant products displayed | High |
| TC_007 | AMZ-SEARCH-002 | Search | Search with invalid keyword | User on homepage | 1. Enter random string 2. Click Search | No results message displayed | Medium |
| TC_008 | AMZ-SEARCH-003 | Search | Apply price filter | Search results displayed | 1. Select price filter | Products filtered by price | Medium |
| TC_009 | AMZ-SEARCH-004 | Search | Sort by price low to high | Search results displayed | 1. Select sort option | Products sorted correctly | Medium |
| TC_010 | AMZ-SEARCH-005 | Search | Search suggestions display | User typing in search bar | 1. Type partial keyword | Auto-suggestions displayed | Low |
| TC_011 | AMZ-CART-001 | Cart | Add product to cart | Product in stock | 1. Select product 2. Click Add to Cart | Product added to cart | High |
| TC_012 | AMZ-CART-002 | Cart | Remove product from cart | Product in cart | 1. Go to Cart 2. Click Delete | Product removed | High |
| TC_013 | AMZ-CART-003 | Cart | Update product quantity | Product in cart | 1. Change quantity | Quantity updated correctly | Medium |
| TC_014 | AMZ-CART-004 | Cart | Add out-of-stock product | Product out of stock | 1. Attempt Add to Cart | Add to Cart disabled | High |
| TC_015 | AMZ-CART-005 | Cart | Verify cart count update | Add product | 1. Add product | Cart icon count increases | Medium |
| TC_016 | AMZ-CHK-001 | Checkout | Proceed to checkout | Product in cart | 1. Click Proceed to Checkout | Checkout page displayed | High |
| TC_017 | AMZ-CHK-002 | Checkout | Add shipping address | Checkout page | 1. Enter address 2. Save | Address saved successfully | High |
| TC_018 | AMZ-CHK-003 | Checkout | Select payment method | Address added | 1. Choose card 2. Continue | Payment method selected | High |
| TC_019 | AMZ-CHK-004 | Checkout | Place order | Payment selected | 1. Click Place Order | Order confirmation page displayed | High |
| TC_020 | AMZ-CHK-005 | Checkout | Invalid card details | On payment page | 1. Enter invalid card 2. Submit | Error message displayed | High |
| TC_021 | AMZ-ORD-001 | Orders | View order history | User logged in | 1. Go to Orders | Past orders displayed | Medium |
| TC_022 | AMZ-ORD-002 | Orders | Cancel order before shipment | Order placed | 1. Click Cancel | Order cancelled successfully | High |
| TC_023 | AMZ-ORD-003 | Orders | Track order | Order shipped | 1. Click Track | Tracking details displayed | Medium |
| TC_024 | AMZ-ORD-004 | Orders | Download invoice | Order delivered | 1. Click Invoice | Invoice downloaded | Low |
| TC_025 | AMZ-ORD-005 | Orders | Return delivered product | Order delivered | 1. Click Return 2. Select reason | Return request submitted | High |
| TC_026 | AMZ-API-001 | API | Verify login API with valid credentials | API endpoint available | 1. Send POST request with valid email/password | 200 OK with auth token returned | High |
| TC_027 | AMZ-API-002 | API | Verify login API with invalid password | API endpoint available | 1. Send POST request with wrong password | 401 Unauthorized response | High |
| TC_028 | AMZ-EDGE-001 | Search | Search with 256 character keyword | User on homepage | 1. Enter 256 char string 2. Click Search | System handles input without crash | Medium |
| TC_029 | AMZ-EDGE-002 | Cart | Add maximum quantity allowed | Product available | 1. Set quantity to maximum limit | System accepts max limit only | Medium |
| TC_030 | AMZ-BND-001 | Registration | Password minimum length boundary | On registration page | 1. Enter password with minimum allowed characters | Password accepted | High |
| TC_031 | AMZ-BND-002 | Registration | Password below minimum length | On registration page | 1. Enter password below minimum limit | Validation error displayed | High |


# 📄 Sheet: RTM

| Requirement ID | Requirement Description | Test Case ID |
| --- | --- | --- |
| AMZ-LOGIN-001 | Valid Login | TC_001, TC_026 |
| AMZ-LOGIN-002 | Invalid Login | TC_002, TC_027 |
| AMZ-CART-001 | Add to Cart | TC_011, TC_029 |
| AMZ-CHK-001 | Checkout | TC_016, TC_019 |
| AMZ-ORD-001 | Order Management | TC_021, TC_025 |
| AMZ-REG-001 | Password Validation | TC_030, TC_031 |


