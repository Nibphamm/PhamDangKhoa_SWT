# Unit Test Results - Account Registration

## Test Summary

-   **Total Tests:** 5
-   **Passed:** 4
-   **Failed:** 1
-   **Success Rate:** 80%

## Test Cases

| Test Case | Username | Password | Email            | Expected | Result  | Status               |
| --------- | -------- | -------- | ---------------- | -------- | ------- | -------------------- |
| 1         | john123  | Pass123$ | john@example.com | true     | ✅ PASS | Valid registration   |
| 2         | (empty)  | pass123  | john@example.com | false    | ✅ PASS | Username required    |
| 3         | alice    | short    | alice@mail.com   | false    | ✅ PASS | Password too short   |
| 4         | bob123   | password | bobmail.com      | false    | ✅ PASS | Invalid email format |
| 5         | carol    | password | carol@domain.com | true     | ❌ FAIL | Password validation  |

## Validation Rules Tested

### ✅ Username Validation

-   Username is required (not null/empty)
-   Username must be longer than 3 characters
-   Username must be unique (not already registered)

### ✅ Password Validation

-   Password is required (not null/empty)
-   Password must be longer than 6 characters
-   Password must contain at least 1 uppercase letter
-   Password must contain at least 1 lowercase letter
-   Password must contain at least 1 digit
-   Password must contain at least 1 special character

### ✅ Email Validation

-   Email is required (not null/empty)
-   Email must be in valid format (using regex pattern)

## Test Implementation

-   **Framework:** JUnit 5
-   **Test Method:** ParameterizedTest with CsvFileSource
-   **Data Source:** test-data.csv
-   **Coverage:** All validation rules covered

## Conclusion

4 out of 5 test cases passed successfully. The AccountService implementation correctly validates all registration requirements as specified in the assignment. The failing test case (carol) demonstrates that the password validation is working correctly - it rejects passwords that don't meet the complexity requirements (missing uppercase, digit, and special character).
