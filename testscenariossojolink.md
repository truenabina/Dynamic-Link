# Feature: Test Scenarios for Sojo Link

## Version:
## Author: QA Team
## Date: 05/02/2025
## Test Manager: Nabina Mainali
## Environment: Staging
## Scope: Functional Testing

## Overview  
This document outlines the test scenarios for the Sojo Link.  

## 1. Login/Signup

## Negative Test Scenarios

## **Scenario 1.1.1: User attempts to sign up with an existing email and receives an appropriate error message**
**Given** the user is on the signup page  
**When** they enter an email that is already registered in the system  
**Then** an error message should be displayed indicating that the email is already in use

---

## **Scenario 1.1.2: User fails to sign up when password and confirm password do not match, and receives an appropriate error message**
**Given** the user is on the signup page  
**When** the user enters a password in the "Password" field  
**And** enters a different value in the "Confirm Password" field  
**Then** an error message should be displayed indicating that the passwords do not match

---

## **Scenario 1.1.3: User attempts login with unverified email and receives verification required error**
**Given** the user has successfully signed up but has not verified their email  
**When** the user enters valid login credentials (email and password) on the login page  
**And** clicks the login button  
**Then** an error message should be displayed stating that email verification is required before logging in

---

## **Scenario 1.1.4: User enters invalid login credentials and receives authentication error**
**Given** the user is on the login page  
**When** the user enters an incorrect email or password  
**Then** an error message should be displayed indicating that the credentials are invalid

---

## **Scenario 1.1.5: User submits unregistered email for password reset and receives 'email not found' error message**
**Given** the user is on the "Forgot Password" page  
**When** the user enters an email address that is not registered in the system  
**Then** an error message should be displayed stating that the email is not found

---

## **Scenario 1.1.6: User enters mismatched passwords during password reset and receives a password mismatch error**
**Given** the user opens the reset password link from their email  
**When** the user enters a new password in the "New Password" field  
**And** enters a different value in the "Confirm Password" field  
**Then** an error message should be displayed stating that the passwords do not match

---

## **Scenario 1.1.7: User submits empty signup form and receives validation errors for required fields**
**Given** the user is on the signup page  
**When** the user leaves any required fields (e.g., name, email, password, confirm password) empty  
**And** clicks the "Sign Up" button  
**Then** individual validation error messages should be displayed for each empty field

---

## Positive Test Scenarios

## **Scenario 1.1.8: User successfully signs up and receives a verification email**
**Given** the user is on the signup page  
**When** the user enters valid values in all required fields (e.g., first name, last name, email, password, and matching confirm password)  
**And** click the "Sign Up" button  
**Then** a verification email should be sent to the entered email address

---

## **Scenario 1.1.9: User clicks verification link and is redirected to login after successful email verification**
**Given** the user clicks the email verification link sent to their registered email  
**When** the verification process completes successfully  
**Then** the user should see a confirmation message "Email verified successfully"  
**And** a "Go to Login" button should be visible to proceed

---

## **Scenario 1.1.10: Verified user logs in with valid credentials and is redirected to the homepage**
**Given** the user has successfully verified their email  
**When** they enter valid email and password and click the "Login" button  
**Then** the user should be redirected to the homepage

---

## **Scenario 1.1.11: User requests password reset and receives a reset link**
**Given** the user is on the login page  
**When** the user clicks “Forgot your password”, enters a valid registered email, and submits the request  
**Then** a password reset link should be sent to the entered email address

---

## **Scenario 1.1.12: User successfully resets their password using the reset link**
**Given** the user clicks the reset link from their email  
**When** the user enters and confirm new password  
**Then** the password should be updated and the user should be redirected to the login page

---

## **Scenario 1.1.13: User clicks on Terms of Service link and is navigated to the respective page**
**Given** the user is on the login or signup page  
**When** the user clicks on "Terms of Service"  
**Then** they should be redirected to a screen displaying Terms of Service content

---

## **Scenario 1.1.14: User clicks on Privacy Policy and is navigated to the respective page**
**Given** the user is on the login or signup page  
**When** the user clicks on the "Privacy Policy"  
**Then** they should be redirected to a screen displaying Privacy Policy content

---

## 2. Creating Dynamic links

## Negative Test Scenarios

## **Scenario 2.1.1: Dynamic link creation fails when required fields are left empty**
**Given** the user is on the Create Dynamic Links form  
**When** the user leaves any required field (e.g., Short code, Deep link URL, Dynamic Link Name) empty  
**And** clicks the Create button  
**Then** a validation error message should be displayed indicating the required field

---

## **Scenario 2.1.2: Dynamic link creation fails when Deep Link URL is in invalid format**
**Given** the user is on the "Create Dynamic Link" form  
**When** the user enters an invalid URL (e.g., www.abcd.com) in the Deep Link URL field  
**Then** an error message should be displayed indicating that the URL format is invalid

---

## **Scenario 2.1.3: User enters a duplicate short code and receives an error message**
**Given** the user is on the "Create Dynamic Link" form  
**And** a dynamic link with the intended short code already exists in the system  
**When** the user enters the same short code into the form  
**And** fills all other required fields with valid inputs  
**And** clicks the "Create" button  
**Then** the system should display an error message stating that the short code is already in use

---

## **Scenario 2.1.4: Validation message is shown when short code exceeds allowed character limit**
**Given** the user is on the "Create Dynamic Link" screen  
**When** the user enters a short-code exceeding the allowed character limit (i.e., 10 characters)  
**Then** a validation error message should be displayed indicating that the short code exceeds the maximum length

---

## **Scenario 2.1.5: Validation message is shown when unsupported character is used in short code**
**Given** the user is on the "Create Dynamic Link" screen  
**When** the user enters a short code containing the # character  
**Then** the system should display a validation message indicating that the character is not allowed in the short code

---

## Positive Test Scenarios

## **Scenario 2.1.6: User creates a dynamic link with valid inputs and the link is generated successfully**
**Given** the user is on the 'Create Dynamic Link' page  
**When** the user enters a valid long URL and a unique short code   
**And** clicks the 'Create' button  
**Then** a new dynamic link should be generated and displayed in the project list

---

## **Scenario 2.1.7: User is redirected to the project’s link list after dynamic link creation**
**Given** the user has successfully created a dynamic link  
**When** the "Link created successfully" popup appears  
**Then** the user should be redirected to the project's dynamic link list page

---

## **Scenario 2.1.8: Dynamic link displays creation date and copy button in project list**
**Given** a dynamic link has been created successfully  
**When** the user navigates to the project list  
**Then** the dynamic link creation date and a copy button adjacent to the dynamic link should be displayed

---

## **Scenario 2.1.9: User successfully updates an existing dynamic link**
**Given** a dynamic link already exists in the project  
**When** the user clicks the "Edit" button and modifies any attribute of the dynamic link (such as the short code, deep link URL, or link behavior)  
**Then** the updated information should be saved and reflected in the dynamic link list

---

## **Scenario 2.1.10: User deletes an existing dynamic link successfully**
**Given** a dynamic link is listed in the project  
**When** the user clicks the delete icon and confirms the deletion from the popup  
**Then** the dynamic link should be removed from the list after confirmation

---

## **Scenario 2.1.11: User successfully copies the dynamic link using the copy button**
**Given** the user is on the project page with a listed dynamic link  
**When** the user clicks the copy button for the dynamic link  
**Then** the dynamic link should be copied to the clipboard  
**And** a confirmation message should appear indicating the link has been copied successfully

---
