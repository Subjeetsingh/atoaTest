# Test Case Documentation

This document outlines the key test cases for various pages such as **Footer Links**, **QRCode Page**, and **Tip Page** in the `AtoaTest` project. Below is a summary of the test cases, objectives, actions, and expected outcomes.

## Test Cases Overview

### 1. **VerifyFooterLink**
**Objective**: Verify the functionalities of the QR Code Page's Footer Links.

| **Action**                         | **Preconditions**         | **Expected Result**                                              | **Assertion**                                                                                                   | **Status** |
|------------------------------------|---------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|------------|
| Verify Navigation to Terms Page    | User is on the QR Code Page | The current URL should be "https://paywithatoa.co.uk/terms/".    | `Assert.assertEquals(driver.getCurrentUrl(), "https://paywithatoa.co.uk/terms/", "Terms page URL does not match!");` | PASS       |
| Verify Navigation to Privacy Policy Page | User is on the QR Code Page | The current URL should be "https://paywithatoa.co.uk/atoa-pay-privacy-policy/". | `Assert.assertEquals(driver.getCurrentUrl(), "https://paywithatoa.co.uk/atoa-pay-privacy-policy/", "Privacy Policy page URL does not match!");` | PASS       |
| Verify Navigation to Help Page     | User is on the QR Code Page | The current URL should be "https://help.paywithatoa.co.uk/".     | `Assert.assertEquals(driver.getCurrentUrl(), "https://help.paywithatoa.co.uk/", "Help page URL does not match!");`  | PASS       |

---

### 2. **QRCodePageTest**
**Objective**: Verify the functionalities of the QR Code Page including content, logo, title, displayed amount, buttons, and footer links.

| **Action**                               | **Preconditions**          | **Expected Result**                                          | **Assertion**                                                                                               | **Status** |
|------------------------------------------|----------------------------|--------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|------------|
| Verify Page Title                        | User is on the QR Code Page | The page title should be "Atoa Instant Bank Pay".             | `Assert.assertEquals(qrCodePage.getPageTitle(), "Atoa Instant Bank Pay", "Page title does not match!");`    | PASS       |
| Verify CRM Image Visibility              | User is on the QR Code Page | The CRM image should be visible.                              | `Assert.assertTrue(qrCodePage.isCRMImageVisible(), "CRM image is not visible.");`                            | PASS       |
| Verify Displayed Amount                  | User is on the QR Code Page | The displayed amount should be "£63.00".                      | `Assert.assertEquals(qrCodePage.getDisplayedAmount(), "£63.00", "Displayed amount does not match!");`        | PASS       |
| Verify Displayed Note                    | User is on the QR Code Page | The displayed note should be "Shubjeet payment".              | `Assert.assertEquals(qrCodePage.getDisplayedNote(), "Shubjeet payment", "Displayed note does not match!");`  | PASS       |
| Verify Submit Button Visibility          | User is on the QR Code Page | The submit button should be visible.                          | `Assert.assertTrue(qrCodePage.isSubmitButtonVisible(), "Submit button is not visible.");`                    | PASS       |
| Verify "How to Pay" Button Visibility    | User is on the QR Code Page | The "How to Pay" button should be visible.                    | `Assert.assertTrue(qrCodePage.isHowToPayButtonVisible(), "How to Pay button is not visible or clickable.");` | PASS       |
| Verify Terms Link Visibility             | User is on the QR Code Page | The Terms link should be visible.                             | `Assert.assertTrue(qrCodePage.isTermsLinkVisible(), "Terms link is not visible or clickable.");`              | PASS       |
| Verify Privacy Policy Link Visibility    | User is on the QR Code Page | The Privacy Policy link should be visible.                    | `Assert.assertTrue(qrCodePage.isPrivacyPolicyLinkVisible(), "Privacy Policy link is not visible or clickable.");` | PASS       |
| Verify Help Link Visibility              | User is on the QR Code Page | The Help link should be visible.                              | `Assert.assertTrue(qrCodePage.isHelpLinkVisible(), "Help link is not visible or clickable.");`                | PASS       |

---

### 3. **TipPageTest**
**Objective**: Validate Tip Selection and Custom Tip Entry. Ensure that users can select predefined tips, enter custom tip amounts, and that the total amount updates correctly.

| **Action**                         | **Preconditions**         | **Expected Result**                                                                                                 | **Assertion**                                                                                                                                       | **Status** |
|------------------------------------|---------------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|------------|
| Navigate to the Tip Page           | User is moving from QR Code page | The user should be successfully redirected to the Tip Page.                                                       | No assertion needed.                                                                                                                                 | PASS       |
| Select the Tip Option              | User is on the Tip Page    | The tip option should be highlighted or marked as selected.                                                         | `Assert.assertEquals(tipPage.getTotalAmount(), "Proceed with £" + String.format("%.2f", expectedTotal), "Expected total should be £" + String.format("%.2f", expectedTotal));` | PASS       |
| Deselect the Tip Option            | User is on the Tip Page    | The tip option should no longer be highlighted.                                                                     | No specific assertion needed.                                                                                                                         | PASS       |
| Check for Custom Tip Option        | User is on the Tip Page    | If the custom tip option is available, the test proceeds; otherwise, it logs a message.                             | Not applicable here.                                                                                                                                 | PASS       |
| Select Custom Tip Option           | User is on the Tip Page    | The custom tip input field becomes visible or active.                                                               | No specific assertion here.                                                                                                                           | PASS       |
| Enter Custom Tip Amount (e.g., £3) | User is on the Tip Page    | The custom tip amount should be accepted in the input field.                                                        | `Assert.assertEquals(tipPage.getTotalAmount(), "Proceed with £" + String.format("%.2f", customExpectedTotal), "Expected total should be £" + String.format("%.2f", customExpectedTotal));` | PASS       |
| Deselect Custom Tip Option         | User is on the Tip Page    | The custom tip option should no longer be selected.                                                                 | No specific assertion needed.                                                                                                                         | PASS       |

---

### Conclusion

These test cases cover a broad range of functionalities, including navigation links, visibility of elements, and validation of dynamic content on the pages. All test cases passed successfully, ensuring the robustness of the QRCode and Tip pages in the application.
