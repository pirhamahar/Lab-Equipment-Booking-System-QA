# Acceptance Criteria
## Lab Equipment Booking and Management System

### 1. Purpose

This document defines the conditions that must be satisfied for the Lab Equipment Booking and Management System to be considered acceptable. Each criterion is based on the functionality of the implemented application.

### 2. Acceptance Criteria

| ID | Feature | Acceptance Criteria | Expected Result |
|---|---|---|---|
| AC-01 | View Equipment | When the user opens the equipment section, the system displays the available equipment. | Equipment names, IDs, and available quantities are displayed. |
| AC-02 | Select Equipment | When the user selects a valid equipment ID, the system recognizes the selected item. | The selected equipment is accepted for booking. |
| AC-03 | Valid Quantity | When the user enters a positive integer within available stock, the system accepts it. | The quantity passes validation. |
| AC-04 | Zero Quantity | When the user enters zero as the booking quantity, the system rejects the request. | An appropriate validation error is displayed. |
| AC-05 | Negative Quantity | When the user enters a negative quantity, the system rejects the request. | An appropriate validation error is displayed. |
| AC-06 | Non-integer Quantity | When the user enters a non-integer quantity, the system rejects the request. | The invalid quantity is not accepted. |
| AC-07 | Excess Quantity | When the requested quantity exceeds available stock, the system rejects the booking. | No booking is created and stock remains unchanged. |
| AC-08 | Invalid Equipment ID | When the user enters an equipment ID that does not exist, the system rejects the booking. | An appropriate error is returned. |
| AC-09 | Valid Booking Date | When the user enters a valid date in YYYY-MM-DD format, the system accepts the date. | Date validation succeeds. |
| AC-10 | Invalid Date Format | When the user enters a date in an incorrect format, the system rejects it. | An appropriate validation error is displayed. |
| AC-11 | Invalid Calendar Date | When the user enters an impossible calendar date, the system rejects it. | The booking is not created. |
| AC-12 | Successful Booking | When all booking details are valid and equipment is available, the user submits the booking. | A booking record is created successfully. |
| AC-13 | Stock Update | After a successful booking, the system updates the equipment quantity. | Available stock decreases by the booked quantity. |
| AC-14 | Booking Record | After a successful booking, the system generates a booking record. | The record contains booking ID, equipment ID, equipment name, quantity, date, and status. |
| AC-15 | View Booking Records | When the user opens booking records, the system displays existing records. | Booking records from the current application session are displayed. |
| AC-16 | Clear Booking Form | When the user selects the Clear option, the booking form is reset. | The form fields are cleared. |
| AC-17 | CLI Equipment Option | When the user selects the equipment viewing option in CLI, the system displays equipment information. | Equipment information is displayed. |
| AC-18 | CLI Booking Option | When the user selects the booking option in CLI and provides valid information, the system processes the booking. | A valid booking is created. |
| AC-19 | CLI Records Option | When the user selects the booking records option, the system displays existing booking records. | Current session records are displayed. |
| AC-20 | CLI Exit Option | When the user selects the exit option, the CLI application terminates. | The application exits normally. |
| AC-21 | Invalid CLI Selection | When the user enters an invalid menu selection, the system handles the input. | An appropriate message is displayed without an unexpected crash. |

### 3. General Acceptance Conditions

The application will be considered acceptable when:

1. All implemented core functions operate as expected.
2. Valid booking information is accepted.
3. Invalid booking information is rejected.
4. Equipment availability is updated correctly after successful bookings.
5. Booking records contain the required information.
6. The GUI and CLI provide the implemented operations.
7. Invalid input is handled without unexpected application termination.

### 4. Testing Evidence

Acceptance of the implemented functionality should be supported by:
- Automated test execution results.
- Test case documentation.
- Defect log.
- Final QA report.

The automated test suite has been reported as passing 29 out of 29 tests. Manual acceptance testing of the GUI should be documented separately.

### 5. Limitations

The acceptance criteria apply to the current implementation. The system does not currently provide permanent database storage, user authentication, booking cancellation, or equipment return functionality.

### 6. Conclusion

The system meets its acceptance conditions when the implemented equipment viewing, booking, validation, stock updating, and booking record features work correctly according to the criteria defined in this document.