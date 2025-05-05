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
**When** the user enters valid values in all required fields: first name, last name, email, password, and matching confirm password  
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

## **Scenario 1.1.13: User clicks on Terms and Conditions link and is navigated to the respective page**
**Given** the user is on the login or signup page  
**When** the user clicks on "Terms and Conditions"  
**Then** they should be redirected to a screen displaying Terms and Conditions content

---

## **Scenario 1.1.14: User clicks on Privacy Policy and is navigated to the respective page**
**Given** the user is on the login or signup page  
**When** the user clicks on the "Privacy Policy"  
**Then** they should be redirected to a screen displaying Privacy Policy content

---