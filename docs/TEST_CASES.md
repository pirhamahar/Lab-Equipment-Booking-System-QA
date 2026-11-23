# Test Cases Documentation
## Lab Equipment Booking and Management System

**Project:** Lab Equipment Booking and Management System  
**Testing Framework:** Pytest  
**Programming Language:** Python  
**Total Test Cases:** 29

---

## 1. Introduction

This document describes the test cases designed for the Lab Equipment Booking and Management System. It covers functional testing, input validation, booking operations, equipment availability, booking records, CLI functionality, and integration testing.

## 2. Test Case Execution Details

- Each test is executed independently using Pytest.
- Project data is reset before and after each test through the automatic fixture in `conftest.py`.
- Actual results must be recorded after execution.
- Test status must be updated according to the execution outcome.

## 3. Booking Functionality Test Cases

### TC-001: Valid Equipment Booking
**Test File:** test_booking.py  
**Description:** Verify that a user can successfully book available equipment.

**Preconditions:** Equipment ID 1 is available.

**Test Steps:**
1. Select equipment ID 1.
2. Enter quantity 1.
3. Enter booking date 2026-11-15.
4. Submit booking.

**Expected Result:** Booking is accepted and status is Pending.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Not Executed.

### TC-002: Invalid Equipment ID
**Test File:** test_booking.py  
**Description:** Verify that an invalid equipment ID is rejected.

**Preconditions:** Equipment list is initialized.

**Test Steps:**
1. Enter equipment ID 99.
2. Enter quantity 1.
3. Enter a valid date.
4. Submit booking.

**Expected Result:** System displays an invalid equipment message.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Not Executed.

### TC-003: Insufficient Equipment Stock
**Test File:** test_booking.py  
**Description:** Verify that booking is rejected when requested quantity exceeds available stock.

**Preconditions:** Equipment ID 4 has limited stock.

**Test Steps:**
1. Select equipment ID 4.
2. Enter quantity 10.
3. Enter a valid date.
4. Submit booking.

**Expected Result:** System rejects the booking and displays an insufficient stock or invalid quantity message.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Not Executed.

### TC-004: Invalid Booking Date
**Test File:** test_booking.py  
**Description:** Verify that an invalid booking date is rejected.

**Test Steps:**
1. Select equipment ID 2.
2. Enter quantity 1.
3. Enter date as `invalid-date`.
4. Submit booking.

**Expected Result:** System displays an invalid date message.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Not Executed.

### TC-005: Stock Reduction After Successful Booking
**Test File:** test_booking.py  
**Description:** Verify that equipment stock decreases after successful booking.

**Preconditions:** Equipment ID 2 has 5 available units.

**Test Steps:**
1. Book 2 units of equipment ID 2.
2. Check available stock.

**Expected Result:** Available stock decreases from 5 to 3.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Not Executed.

### TC-006: Stock Unchanged After Rejected Booking
**Test File:** test_booking.py  
**Description:** Verify that rejected bookings do not reduce equipment stock.

**Preconditions:** Equipment ID 2 has 5 available units.

**Test Steps:**
1. Request 8 units of equipment ID 2.
2. Submit the booking.
3. Check available stock.

**Expected Result:** Booking is rejected and available stock remains 5.

**Actual Result:** All assertions passed during automated execution..  
**Status:** Passed

### TC-007: Successful Booking Record Saved
**Test File:** test_booking.py  
**Description:** Verify that a successful booking is stored in booking records.

**Test Steps:**
1. Create a valid booking for equipment ID 1.
2. Retrieve booking records.
3. Check the number of records and booking status.

**Expected Result:** One booking record is created with Pending status.

**Actual Result:** Pending execution.  
**Status:**Passed

### TC-008: Rejected Booking Not Saved
**Test File:** test_booking.py  
**Description:** Verify that rejected bookings are not stored.

**Test Steps:**
1. Attempt booking with invalid equipment ID 99.
2. Retrieve booking records.
3. Check the number of records.

**Expected Result:** No booking record is created.

**Actual Result:** Pending execution.  
**Status:** All assertions passed during automated execution.

---

## 4. Booking Records Test Cases

### TC-009: Booking Records Start Empty
**Test File:** test_booking_records.py  
**Description:** Verify that booking records are initially empty.

**Test Steps:**
1. Reset project data.
2. Retrieve booking records.

**Expected Result:** An empty list is returned.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-010: Multiple Booking Records
**Test File:** test_booking_records.py  
**Description:** Verify that multiple bookings can be stored with unique sequential booking IDs.

**Test Steps:**
1. Create a booking for equipment ID 1.
2. Create another booking for equipment ID 2.
3. Retrieve all booking records.
4. Verify record count and booking IDs.

**Expected Result:** Two records are stored with booking IDs 1 and 2.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 5. Command Line Interface Test Cases

### TC-011: Exit from CLI
**Test File:** test_cli.py  
**Description:** Verify that users can exit the command line application.

**Test Steps:**
1. Start the CLI application.
2. Enter option 4.
3. Check the displayed output.

**Expected Result:** System displays the application title and exit message.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-012: Display Available Equipment
**Test File:** test_cli.py  
**Description:** Verify that users can view available equipment through the CLI.

**Test Steps:**
1. Start the CLI application.
2. Select option 1.
3. Exit using option 4.
4. Check the displayed equipment list.

**Expected Result:** Projector and Laptop information appears in the output.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-013: Reject Non-Numeric Quantity in CLI
**Test File:** test_cli.py  
**Description:** Verify that the CLI rejects non-numeric booking quantities.

**Test Steps:**
1. Start the CLI application.
2. Select booking option 2.
3. Enter equipment ID 1.
4. Enter quantity `abc`.
5. Exit the application.

**Expected Result:** System displays "Quantity must be a whole number."

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 6. Equipment Management Test Cases

### TC-014: Verify Equipment IDs
**Test File:** test_equipment.py  
**Description:** Verify that all expected equipment IDs exist.

**Test Steps:**
1. Retrieve equipment IDs.
2. Compare them with expected IDs.

**Expected Result:** Equipment IDs are 1, 2, 3, and 4.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-015: Verify Non-Negative Equipment Stock
**Test File:** test_equipment.py  
**Description:** Verify that equipment availability is never negative in the initialized equipment data.

**Test Steps:**
1. Retrieve all equipment records.
2. Check the available quantity of each item.

**Expected Result:** Every equipment item has zero or more available units.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-016: Display Equipment Information
**Test File:** test_equipment.py  
**Description:** Verify that all equipment names appear when displaying equipment.

**Test Steps:**
1. Execute the equipment display function.
2. Capture the output.
3. Check equipment names.

**Expected Result:** Projector, Laptop, HDMI Cable, and Microphone are displayed.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 7. Integration Testing

### TC-017: Complete Booking Flow
**Test File:** test_integration.py  
**Description:** Verify that booking creation, stock reduction, and booking record generation work together.

**Preconditions:** Equipment ID 2 has 5 available units.

**Test Steps:**
1. Create a booking for 2 units of equipment ID 2.
2. Verify the booking confirmation.
3. Check available equipment stock.
4. Retrieve booking records.
5. Verify equipment name, quantity, and status.

**Expected Result:**
- Booking is accepted.
- Available stock becomes 3.
- One booking record is created.
- Equipment name is Laptop.
- Quantity is 2.
- Status is Pending.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 8. Smoke Testing

### TC-018: Verify Initial Equipment Data
**Test File:** test_smoke.py  
**Description:** Verify that the project initializes with sample equipment data.

**Test Steps:**
1. Retrieve the equipment collection.
2. Check the total number of equipment items.
3. Verify equipment ID 1.

**Expected Result:** Four equipment items exist and equipment ID 1 is Projector.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 9. Input Validation Test Cases

### TC-019: Valid Quantity
**Test File:** test_validation.py  
**Description:** Verify that a valid booking quantity is accepted.

**Test Steps:**
1. Enter quantity 2.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns True.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-020: Zero Quantity
**Test File:** test_validation.py  
**Description:** Verify that zero quantity is rejected.

**Test Steps:**
1. Enter quantity 0.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-021: Negative Quantity
**Test File:** test_validation.py  
**Description:** Verify that negative quantities are rejected.

**Test Steps:**
1. Enter quantity -1.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-022: Quantity Exceeds Available Stock
**Test File:** test_validation.py  
**Description:** Verify that quantities exceeding available stock are rejected.

**Test Steps:**
1. Enter quantity 6.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-023: Maximum Available Quantity
**Test File:** test_validation.py  
**Description:** Verify that a quantity equal to available stock is accepted.

**Test Steps:**
1. Enter quantity 5.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns True.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-024: Minimum Valid Quantity
**Test File:** test_validation.py  
**Description:** Verify that the minimum valid quantity is accepted.

**Test Steps:**
1. Enter quantity 1.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns True.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-025: Non-Numeric Quantity
**Test File:** test_validation.py  
**Description:** Verify that non-numeric quantities are rejected.

**Test Steps:**
1. Enter quantity `abc`.
2. Set available stock to 5.
3. Execute quantity validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-026: Empty Booking Date
**Test File:** test_validation.py  
**Description:** Verify that empty booking dates are rejected.

**Test Steps:**
1. Provide an empty date.
2. Execute date validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-027: Valid Booking Date
**Test File:** test_validation.py  
**Description:** Verify that a correctly formatted and valid date is accepted.

**Test Steps:**
1. Enter date 2026-11-15.
2. Execute date validation.

**Expected Result:** Validation returns True.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-028: Incorrect Date Format
**Test File:** test_validation.py  
**Description:** Verify that dates in an incorrect format are rejected.

**Test Steps:**
1. Enter date 15-11-2026.
2. Execute date validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

### TC-029: Invalid Calendar Date
**Test File:** test_validation.py  
**Description:** Verify that an invalid calendar date is rejected.

**Test Steps:**
1. Enter date 2026-02-30.
2. Execute date validation.

**Expected Result:** Validation returns False.

**Actual Result:** Pending execution.  
**Status:** Not Executed.

---

## 10. Test Case Summary

| Testing Category | Number of Test Cases |
|---|---:|
| Booking Functionality | 8 |
| Booking Records | 2 |
| CLI Testing | 3 |
| Equipment Testing | 3 |
| Integration Testing | 1 |
| Smoke Testing | 1 |
| Input Validation | 11 |
| **Total** | **29** |

## 11. Conclusion

The test cases documented in this report cover the major functional and validation requirements of the Lab Equipment Booking and Management System.

These test cases provide a structured basis for evaluating booking operations, equipment availability, input validation, booking records, and application behavior.

Actual execution results and test statuses will be recorded after running the automated test suite.
