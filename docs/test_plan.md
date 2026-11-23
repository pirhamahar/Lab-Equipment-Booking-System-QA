
# Test Plan
## Lab Equipment Booking and Management System

### 1. Introduction
This Test Plan describes the testing approach, scope, objectives, resources, and activities for the Lab Equipment Booking and Management System.

The purpose of testing is to verify that the application correctly displays laboratory equipment, validates booking requests, manages available stock, and maintains booking records.

### 2. Testing Objectives
- Verify that equipment information is displayed correctly.
- Ensure valid booking requests are accepted.
- Verify that invalid booking requests are rejected.
- Ensure equipment stock is updated after successful bookings.
- Verify that rejected bookings do not change available stock.
- Check that booking records are stored correctly.
- Verify quantity and date validation.
- Evaluate application reliability through automated testing.

### 3. Testing Scope

#### 3.1 Features Included
- View available laboratory equipment.
- Display equipment names and stock quantities.
- Book available equipment.
- Validate equipment IDs.
- Validate booking quantities.
- Validate booking dates.
- Update available stock after successful booking.
- Maintain booking records.
- Display booking records.
- Handle invalid CLI inputs.

#### 3.2 Features Excluded
The following features are not included because they are not implemented in the current application:
- User registration and login.
- Booking cancellation.
- Equipment return management.
- Admin equipment management.
- Database-based permanent storage.

### 4. Testing Approach

The following testing techniques will be used:

**4.1 Functional Testing**
Verify that the main application functions produce the expected results.

**4.2 Unit Testing**
Test individual functions such as quantity validation, date validation, and booking creation.

**4.3 Integration Testing**
Verify that booking creation, stock updates, and booking record creation work together correctly.

**4.4 Boundary Value Analysis**
Test quantity values at and around valid boundaries, including:
- Negative quantity (-1)
- Zero quantity (0)
- Minimum valid quantity (1)
- Maximum available stock
- Quantity exceeding available stock

**4.5 Negative Testing**
Test invalid equipment IDs, non-numeric quantities, empty dates, incorrect date formats, and invalid calendar dates.

**4.6 Regression Testing**
Execute the automated test suite again after code changes to ensure existing functionality continues to work.

**4.7 GUI Testing**
Manually inspect the desktop interface on Windows to verify its visual presentation and basic interaction.

### 5. Testing Environment

- Programming Language: Python
- GUI Framework: Tkinter
- Testing Framework: Pytest
- Coverage Tool: Pytest-cov
- Development Environment: Visual Studio Code
- Operating System: Windows (for GUI testing)

### 6. Test Execution

Run the following commands from the project root directory:

Install dependencies:

    python -m pip install -r requirements.txt

Execute automated tests:

    python -m pytest -v

Generate coverage report:

    python -m pytest --cov=src --cov-report=term-missing

### 7. Entry Criteria
- Application source code is available.
- Python environment is configured.
- Required dependencies are installed.
- Test files are available.
- Application modules can be imported successfully.

### 8. Exit Criteria
- All planned automated tests have been executed.
- Test results have been recorded.
- Failed tests, if any, have been investigated.
- Defects have been documented.
- Test execution summary has been prepared.

### 9. Test Deliverables
- Test Plan
- Test Case Documentation
- Boundary Value Analysis Report
- Negative Testing Report
- Defect Log
- Quality Metrics Report
- Final QA Report

### 10. Risks and Limitations
- Booking records are stored in memory and are not permanently saved.
- Equipment stock resets when the application restarts.
- GUI presentation testing requires manual execution.
- The application does not currently provide user authentication or database integration.

### 11. Conclusion
This Test Plan establishes a structured approach to evaluating the Lab Equipment Booking and Management System. Testing will focus on booking correctness, input validation, equipment availability, stock management, and booking record creation.
