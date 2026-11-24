# Requirements-to-Test Traceability Matrix (RTM)
## Lab Equipment Booking and Management System

### 1. Purpose

The purpose of this Requirements-to-Test Traceability Matrix is to establish a relationship between the functional requirements documented in the Software Requirements Specification (SRS) and the corresponding test cases implemented in the project.

It helps identify which requirements have been tested and highlights requirements that still need additional testing.

### 2. Requirements Traceability Matrix

| Requirement ID | Requirement Description | Related Test Case / Test Function | Test File | Coverage Status |
|---|---|---|---|---|
| FR-01 | View available equipment | test_display_equipment | test_equipment.py | Covered |
| FR-02 | Select equipment using its ID | test_valid_booking, test_invalid_equipment | test_booking.py | Covered |
| FR-03 | Enter booking quantity | test_valid_quantity, test_non_numeric_quantity | test_validation.py | Covered |
| FR-04 | Enter booking date | test_valid_date, test_empty_date | test_validation.py | Covered |
| FR-05 | Validate equipment ID | test_invalid_equipment | test_booking.py | Covered |
| FR-06 | Validate booking quantity | test_zero_quantity, test_negative_quantity, test_quantity_exceeds_stock, test_non_numeric_quantity | test_validation.py | Covered |
| FR-07 | Validate booking date | test_wrong_date_format, test_invalid_calendar_date | test_validation.py | Covered |
| FR-08 | Create a booking | test_valid_booking, test_successful_booking_is_saved | test_booking.py | Covered |
| FR-09 | Update equipment availability | test_stock_reduces_after_successful_booking, test_stock_does_not_reduce_after_rejected_booking | test_booking.py | Covered |
| FR-10 | Generate booking record | test_successful_booking_is_saved, test_multiple_booking_records | test_booking.py, test_booking_records.py | Covered |
| FR-11 | View booking records | test_booking_records_start_empty, test_multiple_booking_records | test_booking_records.py | Partially Covered |
| FR-12 | Clear booking form | No automated test identified | Not available | Not Covered |
| FR-13 | CLI interaction | test_cli_can_exit, test_cli_can_display_equipment, test_cli_rejects_non_numeric_quantity | test_cli.py | Partially Covered |

### 3. Additional Test Coverage

The following tests provide additional validation of system behavior:

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

### 4. Coverage Summary

The SRS contains 13 functional requirements.

- Covered: 10 requirements
- Partially Covered: 2 requirements
- Not Covered: 1 requirement

**Note:** These are requirement-level coverage classifications, not the automated test pass rate. Partially covered requirements have some related automated tests, but their complete functionality is not verified by those tests.

### 5. Test Execution Results

According to the reported automated test execution:

| Metric | Result |
|---|---|
| Total Automated Tests | 29 |
| Passed Tests | 29 |
| Failed Tests | 0 |
| Automated Test Pass Rate | 100% |

Test Pass Rate = (Passed Tests / Total Tests) × 100

Test Pass Rate = (29 / 29) × 100 = 100%

### 6. Coverage Gaps and Recommendations

The following areas require additional testing:

1. Add a GUI test to verify that the Clear button resets all booking form fields.
2. Add tests to verify the complete booking records display functionality.
3. Add CLI tests for booking records and invalid menu selections.
4. Perform manual GUI testing to verify navigation, booking form behavior, and error messages.
5. Update this matrix when additional tests are implemented.

### 7. Conclusion

The traceability matrix links the system's functional requirements with the available automated tests. The reported automated test results show that all 29 tests passed. However, some requirements need additional automated or manual testing to achieve complete verification.