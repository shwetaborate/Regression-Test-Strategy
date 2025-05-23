# Regression Test Strategy
**Created by:** Shweta Borate  
**Contact:** shwetalh1993@gmail.com  

## Problem Statement
A new major version adding new functionality is being released. You are responsible for developing the regression tests for the existing end-user-facing functionality that was not intentionally changed but may have been impacted since there was a major refactor performed at the data and user interface layers.

### Please provide the following:
- Overall test strategy including main areas of focus.
- Example test cases for main areas of focus.
- Identify the automation tool which can be used to automate above and justify your decision with 4-5 points.

## Test Strategy for Regression Testing Amazon Shopping Website

### **Objective**
To ensure that existing end-user-facing functionality continues to work as expected after a major refactor of the data and UI layers.

### **Test Website**: [here](https://www.amazon.in/?&tag=googhydrabk1-21&ref=pd_sl_5szpgfto9i_e&adgrpid=155259813593&hvpone=&hvptwo=&hvadid=674893540034&hvpos=&hvnetw=g&hvrand=12482784497165071722&hvqmt=e&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9062097&hvtargid=kwd-64107830&hydadcr=14452_2316413&gad_source=1)

### **Overall Strategy**
- **Risk-based regression testing:** Prioritize features that are most critical to the user experience and business.
- **Automation-first:** Automate repeatable regression scenarios to ensure rapid feedback.
- **Cross-platform validation:** Validate core functionalities on different devices (Android, iOS, Web).
- **Data consistency checks:** Verify data retrieved via APIs and displayed in the UI is accurate.

### **Test Execution Strategy**
- **Smoke Testing:** Critical paths like login, search, add to cart to ensure basic functionalities are usable.
- **Sanity Testing:** High-traffic flows like purchase, Wishlist, reviews.
- **Full Regression Testing:** All major modules post sanity pass.
- Some **Performance and Load Testing** test cases may be included depending on the new feature.

## **Main Areas of Focus**
- **Login & Authentication**
- **Search and Product Listing**
- **Product Details Page**
- **Cart and Checkout**
- **Order History & Tracking**
- **Wishlist & Saved Items**
- **Payments & Address Management**
- **Localization & Currency**
- **Push Notifications & Alerts**
- **UI Consistency & Responsiveness**

---

## **Example Test Cases**
| Test ID | Test Title | Focus Area | Priority |
|---------|------------|-------------|-----------|
| TC-001 | Complete Purchase Flow | Core User Journey Integrity | Critical |
| TC-002 | Guest Checkout Process | Core User Journey Integrity | Critical |
| TC-003 | Product Information Accuracy | Data Consistency & Integration | Critical |
| TC-004 | Real-time Inventory Updates | Data Consistency & Integration | Critical |
| TC-005 | Search Functionality | UI Component Functionality | High |
| TC-006 | Cross-Platform UI Validation | UI Component Functionality | High |
| TC-007 | Page Load Performance | Performance & Load Characteristics | High |
| TC-008 | Concurrent User Load | Performance & Load Characteristics | High |
| TC-009 | Payment Processing Integration | Integration Points & APIs | Medium-High |
| TC-010 | Recommendation Engine Integration | Integration Points & APIs | Medium-High |

### **Core User Journey Integrity**
#### **TC-001: Complete Purchase Flow**
**Objective:** Verify end-to-end purchase process functionality  
**Steps:**
1. Navigate to Amazon homepage
2. Search for "iPhone 15 Pro"
3. Select product from search results
4. Add item to cart with quantity 2
5. Proceed to checkout
6. Enter shipping address
7. Select shipping method
8. Enter payment information
9. Review order summary
10. Place order

**Expected Results:**
- Order confirmation displayed
- Confirmation email received
- Order appears in account history
- Inventory decremented correctly

#### **TC-002: Guest Checkout Process**
**Objective:** Ensure guest users can complete purchases without account creation  
**Steps:**
1. Add product to cart without logging in
2. Proceed to checkout as guest
3. Complete purchase flow  

**Expected Results:** Order processed successfully without requiring account creation

---

### **Data Consistency & Integration**
#### **TC-003: Product Information Accuracy**
**Objective:** Verify product data displays correctly across all touchpoints  
**Steps:**
1. Access product via search
2. Access same product via category browse
3. Access product via recommendation
4. Compare product details, pricing, and availability  

**Expected Results:** Consistent product information across all access methods

#### **TC-004: Real-time Inventory Updates**
**Objective:** Ensure inventory changes reflect immediately across the platform  
**Test Data:** Product with limited stock (≤5 units)  
**Steps:**
1. Note current inventory level
2. Add maximum available quantity to cart
3. Verify inventory shows "out of stock"
4. Remove items from cart
5. Verify inventory updates reflect availability  

**Expected Results:** Real-time inventory updates across all user interfaces

---

### **UI Component Functionality**
#### **TC-005: Search Functionality**
**Objective:** Verify search components work correctly post-UI refactor  
**Steps:**
1. Perform keyword search ("wireless headphones")
2. Apply filters (brand, price range, ratings)
3. Sort results (price low-to-high, customer reviews)
4. Verify pagination functionality  

**Expected Results:**  
- Relevant results displayed  
- Filters apply correctly  
- Sorting functions properly  
- Pagination works smoothly  

---

### **Performance & Load Characteristics**
#### **TC-007: Page Load Performance**
**Objective:** Verify acceptable performance after architectural changes  
**Pages to Test:** Homepage, Product detail pages, Search results, Checkout pages  

**Metrics:**
- First Contentful Paint < 2 seconds
- Largest Contentful Paint < 4 seconds
- Total page load < 5 seconds  

**Expected Results:** All pages meet or exceed baseline performance metrics  

---

## **Automation Tool Selection**
- **Selenium WebDriver**
- **Appium**
- **TestNG**
- **Maven**
- **RestAssured** (for API testing)
- **Lighthouse** (performance analysis)
- **JMeter/Gatling** (load testing)

### **Justification for Selenium & Appium Selection**
1. **Cross Platform Coverage:** Selenium WebDriver provides robust web browser automation across Chrome, Firefox, Safari, and Edge, while Appium enables native mobile app testing on iOS and Android. This ensures comprehensive cross-platform coverage. 
2. **Industry Standard:** Selenium is the most widely adopted automation framework with extensive community support, comprehensive documentation, and proven stability in enterprise environments.  
3. **Language Flexibility:** Both tools being largely language agnostic (Java, Python, JavaScript, C#, Ruby) ensures flexibility and easy adoption.  
4. **Advanced Mobile Testing Capabilities:** Appium's ability to test both native mobile apps and mobile web experiences using the same WebDriver API provides consistency in test development and maintenance. 
5. **Cost Effective:** Open-source tools ensure minimal tool costs.  
6. **CI/CD Friendly:** Integrates seamlessly with Jenkins, GitHub Actions.  
7. **Unified Framework & Reusability:** Can be integrated into a single Maven project with TestNG & POM structure.  
8. **RestAssured for API Testing:** Easy integration into Selenium framework for API validations.  

---
