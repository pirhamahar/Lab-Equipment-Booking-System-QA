# Requirements-to-Test Traceability Matrix (RTM)
## Lab Equipment Booking and Management System

### 1. Purpose

The purpose of this Requirements-to-Test Traceability Matrix is to establish a relationship between the functional requirements documented in the Software Requirements Specification (SRS) and the corresponding automated and manual test cases performed for the project.

This matrix helps verify requirement coverage, identify testing gaps, and ensure that the documented system requirements have been tested through appropriate testing activities.

### 2. Requirements Traceability Matrix

| Requirement ID | Requirement Description | Related Automated Test Function | Test File | Related Manual GUI Test | Coverage Status |
|---|---|---|---|---|---|
| FR-01 | View available equipment | test_display_equipment | test_equipment.py | GUI-03 | Covered |
| FR-02 | Select equipment using its ID | test_valid_booking, test_invalid_equipment | test_booking.py | GUI-05 | Covered |
| FR-03 | Enter booking quantity | test_valid_quantity, test_non_numeric_quantity | test_validation.py | GUI-05, GUI-06 | Covered |
| FR-04 | Enter booking date | test_valid_date, test_empty_date | test_validation.py | GUI-05, GUI-07 | Covered |
| FR-05 | Validate equipment ID | test_invalid_equipment | test_booking.py | Not separately tested | Covered |
| FR-06 | Validate booking quantity | test_zero_quantity, test_negative_quantity, test_quantity_exceeds_stock, test_non_numeric_quantity | test_validation.py | GUI-06, GUI-08 | Covered |
| FR-07 | Validate booking date | test_wrong_date_format, test_invalid_calendar_date | test_validation.py | GUI-07 | Covered |
| FR-08 | Create a booking | test_valid_booking, test_successful_booking_is_saved | test_booking.py | GUI-05 | Covered |
| FR-09 | Update equipment availability | test_stock_reduces_after_successful_booking, test_stock_does_not_reduce_after_rejected_booking | test_booking.py | GUI-09 | Covered |
| FR-10 | Generate booking record | test_successful_booking_is_saved, test_multiple_booking_records | test_booking.py, test_booking_records.py | GUI-05, GUI-10 | Covered |
| FR-11 | View booking records | test_booking_records_start_empty, test_multiple_booking_records | test_booking_records.py | GUI-10 | Covered |
| FR-12 | Clear booking form | No automated test identified | Not available | Not separately tested | Not Covered |
| FR-13 | CLI interaction | test_cli_can_exit, test_cli_can_display_equipment, test_cli_rejects_non_numeric_quantity | test_cli.py | Not applicable | Partially Covered |

**Note:** Coverage classifications consider both automated test execution and the documented manual GUI testing results. Requirements marked Partially Covered or Not Covered still require additional verification.

### 3. Additional Automated Test Coverage

The following automated tests provide additional validation of system behavior:

| Test Function | Test File | Purpose |
|---|---|---|
| test_insufficient_stock | test_booking.py | Checks booking rejection when stock is insufficient. |
| test_invalid_date | test_booking.py | Checks rejection of invalid booking dates. |
| test_rejected_booking_is_not_saved | test_booking.py | Ensures rejected bookings are not recorded. |
| test_equipment_ids_exist | test_equipment.py | Checks that expected equipment IDs exist. |
| test_equipment_have_non_negative_stock | test_equipment.py | Checks that equipment stock is not negative. |
| test_complete_booking_flow_updates_stock_and_record | test_integration.py | Checks the complete booking process, stock update, and record creation. |
| test_project_has_sample_equipment | test_smoke.py | Checks that sample equipment is available. |
| test_maximum_available_quantity | test_validation.py | Checks acceptance of a quantity equal to available stock. |
| test_minimum_valid_quantity | test_validation.py | Checks acceptance of the minimum valid quantity. |
| test_booking_records_start_empty | test_booking_records.py | Verifies that booking records initially contain no entries. |
| test_multiple_booking_records | test_booking_records.py | Verifies that multiple booking records can be maintained. |

### 4. Manual GUI Test Coverage

The following manual GUI test cases were executed to verify the application's graphical interface and booking functionality.

| Test ID | Test Scenario | Result |
|---|---|---|
| GUI-01 | Launch the desktop application | Passed |
| GUI-02 | Open Dashboard | Passed |
| GUI-03 | Open Equipment page | Passed |
| GUI-04 | Open New Booking page | Passed |
| GUI-05 | Submit a valid booking | Passed |
| GUI-06 | Enter invalid quantity | Passed |
| GUI-07 | Enter invalid booking date | Passed |
| GUI-08 | Request quantity greater than available stock | Passed |
| GUI-09 | Verify stock after successful booking | Passed |
| GUI-10 | Open Booking Records | Passed |
| GUI-11 | Verify booking status | Passed |

All 11 documented manual GUI test cases passed during testing.

### 5. Coverage Summary

The SRS contains 13 functional requirements.

| Coverage Status | Number of Requirements |
|---|---:|
| Covered | 11 |
| Partially Covered | 1 |
| Not Covered | 1 |
| **Total Functional Requirements** | **13** |

**Requirement Coverage Calculation:**

Fully Covered Requirements / Total Functional Requirements × 100

(11 / 13) × 100 = 84.62%

This percentage represents fully covered functional requirements only. It is separate from the test execution pass rate.

### 6. Test Execution Results

According to the reported automated and manual test execution results:

| Testing Type | Total Tests | Passed | Failed |
|---|---:|---:|---:|
| Automated Testing | 29 | 29 | 0 |
| Manual GUI Testing | 11 | 11 | 0 |
| **Total** | **40** | **40** | **0** |

**Overall Test Pass Rate:**

(Passed Tests / Total Executed Tests) × 100

(40 / 40) × 100 = 100%

### 7. Coverage Gaps and Recommendations

The following areas require additional testing or verification:

1. Add an automated or manual GUI test to verify that the Clear button resets the booking form fields.
2. Add automated tests for displaying booking records through the CLI.
3. Add automated tests for invalid CLI menu selections.
4. Add additional exploratory GUI tests for navigation, form interactions, and error messages.
5. Update this matrix whenever new requirements or test cases are implemented.

### 8. Conclusion

The Requirements-to-Test Traceability Matrix establishes a relationship between the 13 functional requirements documented in the SRS and their corresponding automated and manual test cases.

A total of 11 functional requirements are classified as Covered, one as Partially Covered, and one as Not Covered.

The reported testing results show that all 29 automated test cases and all 11 manual GUI test cases passed, resulting in an overall test pass rate of 100%.

Although the documented testing activities provide strong verification of the implemented functionality, additional testing is recommended for the remaining coverage gaps, particularly the Clear Booking Form functionality and incomplete CLI interaction scenarios.

**Document Status:** Updated with Automated and Manual GUI Testing Results.