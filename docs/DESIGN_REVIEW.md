# Design Review
## Lab Equipment Booking and Management System

### 1. Introduction

The purpose of this design review is to evaluate the software structure, module organization, user interface, booking process, validation logic, and maintainability of the Lab Equipment Booking and Management System.

The review identifies the strengths, design limitations, and areas that can be improved in the current implementation.

### 2. System Architecture Overview

The application follows a modular Python-based design. Its functionality is divided into separate modules responsible for the graphical interface, command-line interaction, equipment management, booking operations, and input validation.

#### 2.1 Main Components

| Component | File | Responsibility |
|---|---|---|
| Graphical User Interface | app_gui.py | Provides the desktop interface, dashboard, equipment listing, booking form, and booking records. |
| Booking Management | booking.py | Processes booking requests, updates stock, and creates booking records. |
| Equipment Management | equipment.py | Stores equipment information and provides equipment-related functions. |
| Input Validation | validation.py | Validates booking quantities and booking dates. |
| Application Entry Point | main.py | Starts the GUI or CLI application based on the execution option. |

#### 2.2 Architecture Description

The GUI and CLI provide two different ways to interact with the application. Both use the booking and equipment modules to perform the core operations.

The booking module uses the validation module before accepting a booking. Once the booking is accepted, the equipment quantity is reduced and a booking record is created.

### 3. Design Evaluation

#### 3.1 Modular Structure

**Observation:**

The application separates major responsibilities into different Python modules.

**Strengths:**
- Booking operations are separated from the user interface.
- Equipment information is maintained in a dedicated module.
- Validation logic is reusable.
- The GUI and CLI use common booking functionality.

**Recommendation:**

Continue maintaining this modular structure and avoid placing all business logic inside the interface code.

#### 3.2 User Interface Design

**Observation:**

The application uses Tkinter to provide a desktop interface with a sidebar and four main sections:
- Dashboard
- Equipment
- New Booking
- Booking Records

The dashboard displays equipment types, available items, total bookings, and pending bookings.

**Strengths:**
- Navigation options are clearly separated.
- Equipment information is displayed in tables.
- The booking form provides equipment selection, quantity, and date fields.
- Error and success messages are displayed through message boxes.

**Recommendation:**

Add automated GUI tests to verify navigation, form submission, validation messages, and the Clear button.

#### 3.3 Booking Logic

**Observation:**

The `create_booking()` function in `booking.py` checks the equipment ID, quantity, and booking date before processing a request.

For a successful booking, it reduces the available stock and creates a record with a booking ID and Pending status.

**Strengths:**
- Invalid equipment IDs are rejected.
- Invalid quantities and insufficient stock are rejected.
- Invalid booking dates are rejected.
- Stock is updated only after successful validation.

**Recommendation:**

Introduce persistent storage in a future version so that booking records and equipment quantities are retained after the application closes.

#### 3.4 Input Validation

**Observation:**

The `validation.py` module provides two main functions:
- `validate_quantity()`
- `validate_date()`

Quantity validation checks that the value is an integer greater than zero and does not exceed available stock. Date validation checks the YYYY-MM-DD format and calendar validity.

**Strengths:**
- Validation is separated from booking logic.
- Invalid quantities are rejected.
- Invalid date formats and calendar dates are rejected.
- Boolean values are not accepted as quantities.

**Recommendation:**

Additional validation rules can be introduced when the booking requirements are expanded.

#### 3.5 Data Management

**Observation:**

Equipment information is stored in a Python dictionary, while booking records are maintained in an in-memory list.

**Strengths:**
- Data structures are simple and easy to understand.
- Equipment availability can be updated directly.
- Booking records can be retrieved during the active session.

**Limitations:**
- Data is not stored permanently.
- Booking records are lost when the application restarts.
- There is no database integration.
- The application does not provide user authentication.

**Recommendation:**

Consider integrating SQLite or another database in a future version to support permanent data storage.

### 4. Design Strengths

The following positive design characteristics were identified:

1. Modular organization of application functionality.
2. Reusable booking logic for GUI and CLI operations.
3. Separate input validation functions.
4. Clear navigation between the main GUI sections.
5. Equipment stock is updated after successful bookings.
6. Error handling is provided for invalid booking information.
7. The application supports both GUI and CLI execution.

### 5. Design Weaknesses and Improvement Areas

| ID | Identified Area | Current Limitation | Recommended Improvement |
|---|---|---|---|
| DR-01 | Data Persistence | Application data is stored in memory. | Integrate a database such as SQLite. |
| DR-02 | User Authentication | No login or user account functionality exists. | Introduce authentication if required. |
| DR-03 | Booking Management | Booking cancellation and equipment return are not implemented. | Add booking cancellation and return operations. |
| DR-04 | GUI Testing | Automated GUI behavior is not established by the current test suite. | Add GUI-focused tests. |
| DR-05 | Booking History | Booking records are limited to the current session. | Store booking history permanently. |
| DR-06 | Data Management | Equipment information is defined directly in Python code. | Support equipment management through persistent storage. |

### 6. Software Quality Considerations

The current design was reviewed against the following software quality characteristics:

| Quality Attribute | Review |
|---|---|
| Maintainability | Modular files make the application easier to understand and modify. |
| Usability | The Tkinter interface provides clear navigation and booking options. |
| Reliability | Booking validation helps prevent invalid requests and incorrect stock updates. |
| Performance | The application uses simple in-memory data structures for its main operations. |
| Portability | Python and Tkinter support execution on compatible operating systems. |
| Data Integrity | Booking validation and stock updates help maintain correct quantities during an active session. |

### 7. Overall Design Review Findings

The current application has a clear modular structure and provides the main functionality required for basic laboratory equipment booking.

The separation of the GUI, CLI, booking operations, equipment information, and validation logic is a positive design decision.

However, the application has limitations related to data persistence, authentication, booking lifecycle management, and automated GUI testing.

These limitations should be considered when planning future improvements.

### 8. Conclusion

The design review indicates that the Lab Equipment Booking and Management System provides a functional foundation for laboratory equipment booking and management.

Its modular architecture, reusable booking logic, and input validation support maintainability and basic reliability.

Future development should focus on database integration, improved booking management, authentication where required, and additional GUI testing to improve the overall quality of the application.