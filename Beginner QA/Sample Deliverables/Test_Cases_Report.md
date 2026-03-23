# 📄 Sheet: Risk Based Testing

| TC_ID | Feature | Risk Level | Test Scenario | Test Steps | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- |
| TC_RISK_01 | Login | High | Invalid login attempts | Enter wrong password multiple times | Account should lock | High |
| TC_RISK_02 | Payment | High | Payment failure handling | Enter invalid card details | Error message shown | High |
| TC_RISK_03 | Search | Medium | Search performance | Search common product | Results should load quickly | Medium |
| TC_RISK_04 | Cart | High | Add high quantity | Add 100 items | System should handle or restrict | High |
| TC_RISK_05 | Profile | Low | Update profile | Change name | Profile updated successfully | Low |


# 📄 Sheet: Decision Table

| Condition: Login Valid | Condition: OTP Valid | Action: Allow Access |
| --- | --- | --- |
| Yes | Yes | Allow |
| Yes | No | Deny |
| No | Yes | Deny |
| No | No | Deny |


# 📄 Sheet: BVA_Equivalence_Negative

| TC_ID | Field | Input Value | Type | Expected Result |
| --- | --- | --- | --- | --- |
| TC_BVA_01 | Age | 17 | Invalid (<18) | Error |
| TC_BVA_02 | Age | 18 | Valid Boundary | Accepted |
| TC_BVA_03 | Age | 60 | Valid Boundary | Accepted |
| TC_BVA_04 | Age | 61 | Invalid (>60) | Error |
| TC_EQ_01 | Age | 25 | Valid Partition | Accepted |
| TC_EQ_02 | Age | 10 | Invalid Partition | Error |
| TC_NG_03 |  | # | Negative Testing | Error |
| TC_NG_04 |  | NA | Negative Testing | Error |


# 📄 Sheet: Student Task

| Student Task: |
| --- |
|  |
| Create: |
|  |
| 5 Risk-based test cases for Amazon Checkout |
|  |
| 1 Decision table for Payment method selection |
|  |
| 6 BVA test cases for price filter (₹1–₹10,000) |


