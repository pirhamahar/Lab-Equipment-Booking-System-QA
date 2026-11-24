# Software Requirements Specification (SRS)
## Lab Equipment Booking and Management System

### 1. Introduction

#### 1.1 Purpose
The purpose of this Software Requirements Specification (SRS) is to describe the functional and non-functional requirements of the Lab Equipment Booking and Management System. The system allows users to view available laboratory equipment, make equipment bookings, and view booking records.

#### 1.2 Project Scope
The Lab Equipment Booking and Management System is a Python-based application developed to manage laboratory equipment bookings. It provides a graphical user interface (GUI) using Tkinter and a command-line interface (CLI).

The system supports:
- Viewing available laboratory equipment.
- Booking equipment by selecting its ID, quantity, and booking date.
- Validating booking information.
- Updating equipment availability after successful bookings.
- Viewing existing booking records.

#### 1.3 Intended Audience
This document is intended for:
- Project developers.
- Software testers and quality assurance team members.
- Project evaluators and instructors.
- Users of the application.

### 2. Overall Description

#### 2.1 Product Perspective
The system is a standalone Python application. It provides GUI-based and CLI-based interaction. Booking records and equipment availability are maintained in application memory during execution.

#### 2.2 User Classes
**General User:** A person who uses the application to view equipment, make bookings, and check booking records.

#### 2.3 Operating Environment
- Operating System: Windows, Linux, or macOS with Python support.
- Programming Language: Python.
- GUI Framework: Tkinter.
- Testing Framework: Pytest.
- Python Version: Python 3.10 or later.

### 3. Functional Requirements

**FR-01: View Equipment**

The system shall allow users to view the available laboratory equipment and its current stock.

**FR-02: Select Equipment**

The system shall allow users to select equipment using its equipment ID.

**FR-03: Enter Booking Quantity**

The system shall allow users to enter the required quantity of selected equipment.

**FR-04: Enter Booking Date**

The system shall allow users to provide a booking date in YYYY-MM-DD format.

**FR-05: Validate Equipment ID**

The system shall verify that the selected equipment ID exists before processing a booking.

**FR-06: Validate Booking Quantity**

The system shall reject quantities that are not valid positive integers or exceed the available equipment quantity.

**FR-07: Validate Booking Date**

The system shall validate the booking date and reject invalid dates or dates that do not follow the required YYYY-MM-DD format.

**FR-08: Create Booking**

The system shall create a booking record when all booking information is valid and sufficient equipment is available.

**FR-09: Update Equipment Availability**

The system shall decrease the available equipment quantity after a successful booking.

**FR-10: Generate Booking Record**

The system shall generate a booking record containing booking ID, equipment ID, equipment name, quantity, booking date, and booking status.

**FR-11: View Booking Records**

The system shall allow users to view previously created booking records during the current application session.

**FR-12: Clear Booking Form**

The GUI shall provide a clear option to reset the booking form fields.

**FR-13: CLI Interaction**

The system shall provide command-line options to view equipment, book equipment, view booking records, and exit the application.

### 4. Non-Functional Requirements

**NFR-01: Usability**

The application should provide understandable navigation and clear options for users.

**NFR-02: Reliability**

The system should process valid booking requests correctly and prevent invalid booking information from being accepted.

**NFR-03: Performance**

The system should respond to normal user operations without unnecessary delays.

**NFR-04: Maintainability**

The source code should be organized into separate modules for equipment, booking, validation, and application functionality.

**NFR-05: Portability**

The application should be executable on operating systems that support the required Python version and Tkinter.

**NFR-06: Data Integrity**

The system should maintain correct equipment quantities during the application session and should not create a booking when validation fails.

### 5. System Constraints

- Python must be installed to execute the application.
- Tkinter must be available for GUI execution.
- The application maintains booking records and stock changes in memory.
- Booking records and stock updates are not permanently stored and are reset when the application restarts.
- The system does not provide user authentication or role-based access.
- The system does not currently provide equipment cancellation or return functionality.

### 6. Inputs and Outputs

#### 6.1 Inputs
- Equipment ID.
- Equipment quantity.
- Booking date.

#### 6.2 Outputs
- Equipment listing with available quantities.
- Booking confirmation or validation error messages.
- Updated equipment availability.
- Booking records containing booking details and status.

### 7. Validation Requirements

The system shall apply the following validation rules:

- Equipment ID must correspond to an existing equipment item.
- Quantity must be a positive integer.
- Quantity must not exceed the available stock.
- Booking date must be a valid calendar date.
- Booking date must follow the YYYY-MM-DD format.
- Invalid input must not result in a successful booking.

### 8. Error Handling

The system should handle invalid user input and display appropriate error messages.

Examples include:
- Invalid equipment ID.
- Non-integer quantity.
- Zero or negative quantity.
- Quantity greater than available stock.
- Incorrect date format.
- Invalid calendar date.
- Invalid CLI menu selection.

### 9. Assumptions

- Users have basic knowledge of operating a desktop application.
- Users provide the correct equipment information and booking date.
- The required Python environment is available.
- The application is used for managing bookings during its active session.

### 10. Limitations

- Booking information is not permanently saved.
- The system does not include a database.
- The system does not support login or user account management.
- The system does not provide booking cancellation or equipment return features.
- The system does not provide an online or network-based booking service.

### 11. Conclusion

The Lab Equipment Booking and Management System provides basic functionality for viewing laboratory equipment, validating booking requests, managing available quantities, and displaying booking records. This SRS documents the requirements and limitations of the implemented application and provides a basis for software testing and quality assurance activities.