
# GUI Manual Testing Report

## 1. Overview

This report documents the manual testing performed on the Lab Equipment Booking and Management System desktop GUI.

The purpose was to verify that the application's graphical interface, navigation, equipment display, booking functionality, input validation, and booking records work as expected.

## 2. Testing Environment

- Application: Lab Equipment Booking and Management System
- Interface: Python Tkinter Desktop GUI
- Operating System: Windows
- Testing Type: Manual GUI Testing

## 3. Manual Test Results

| Test ID | Test Scenario | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| GUI-01 | Launch the desktop application | Application opens successfully | Application opened successfully | Passed |
| GUI-02 | Open Dashboard | Dashboard displays equipment and booking summaries | Dashboard displayed correctly | Passed |
| GUI-03 | Open Equipment page | Equipment list and available quantities are displayed | Equipment information displayed correctly | Passed |
| GUI-04 | Open New Booking page | Booking form is displayed | Booking form opened successfully | Passed |
| GUI-05 | Submit a valid booking | Booking is created successfully | Booking was created successfully | Passed |
| GUI-06 | Enter invalid quantity | System rejects invalid quantity | Invalid quantity was rejected | Passed |
| GUI-07 | Enter invalid booking date | System rejects invalid date | Invalid date was rejected | Passed |
| GUI-08 | Request quantity greater than available stock | System rejects the booking | Insufficient stock booking was rejected | Passed |
| GUI-09 | Verify stock after successful booking | Available stock decreases accordingly | Available stock updated correctly | Passed |
| GUI-10 | Open Booking Records | Saved booking details are displayed | Booking records displayed correctly | Passed |
| GUI-11 | Verify booking status | New booking displays Pending status | Pending status displayed correctly | Passed |

## 4. Test Summary

- Total Manual Test Cases: 11
- Passed: 11
- Failed: 0
- Blocked: 0

## 5. Observations

- The desktop application launched successfully.
- Dashboard displayed equipment and booking summaries.
- Equipment information and available quantities were displayed correctly.
- Valid booking requests were processed successfully.
- Invalid input and insufficient stock were rejected.
- Equipment availability was updated after successful bookings.
- Booking records displayed the submitted booking information and Pending status.

## 6. Conclusion

All 11 manual GUI test cases passed during testing. The application successfully demonstrated its main graphical interface features, equipment management display, booking operations, input validation, stock updates, and booking record display.

The manual testing results support the successful verification of the tested GUI functionality.
