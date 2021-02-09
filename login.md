---
layout: default title: Log in user story example
permalink: /examples/login
nav_order: 3
---

# Log in user story examples

Here are a set of example user stories for an application log in. This user story example will include user stories and acceptance criteria covering:

- User access
- Log in navigation
- Form input and validation
- Password recovery

# Backlog

| ID | Summary | Description | Epic |
| --- | --- | --- | --- |
| LOG-1 | Access the application securely | As a user, I want to access the application securely, to protect my information | Login |
| LOG-2 | Navigate to log in | As a user, I want to navigate to the login form, so that I can enter my credentials | Login |
| LOG-3 | Enter credentials | As a user, I want to enter my credentials, so I can submit the form | Login |
| LOG-4 | Reset password | As a user, I want to reset my password, so that I recover access my account | Login |

# Stories and Acceptance Criteria

## Login

Epic {: .ml-0 .mb-0 .label .label-purple }

As a user, I want to login, to access the application and my information

## Access the application securely

Story LOG-1 {: .ml-0 .mb-0 .label .label-green }

As a user, I want to access the application securely, to protect my information

**Acceptance criteria**

```
Feature: Access

Scenario: Access denied
  Given I am not logged in
  When I navigate to access the application
  Then I see "Access denied"
  And I am unable to my secure information

Scenario: Access permitted
  Given I have logged in
  When I navigate to access the application
  Then I can access my secure information
```

## Navigate to log in

Story LOG-2 {: .ml-0 .mb-0 .label .label-green }

As a user, I want to navigate to the login form, so that I can enter my credentials

**Acceptance criteria**

```
Feature: Navigation

Scenario: Navigate to login
  Given I am not logged in
  When I visit the application
  Then I see a button to "Log in"
  When I select "Log in"
  Then I navigate to the log in screen
  And I see the screen name "Log in"

Scenario: Navigate to log out
  Given I am logged in
  When I visit the application
  Then I see a button to "Log out"
  When I select "Log out"
  Then I am logged out
  And I see a message of "Log out successful"

```

## Enter credentials

Story LOG-3 {: .ml-0 .mb-0 .label .label-green }

As a user, I want to enter my credentials, so I can submit the form

```
Feature: Form

Scenario: See form
  Given I have selected to "Login"
  When I am on the login screen
  Then I see a form field labelled "email"
  And I see a form field labelled "Password"
  And I see a button to "Submit"

Scenario: Enter valid email
  When I enter an email
  And the email has a prefix
  And the email has an @ symbol proceed the prefix
  And the email has a suffix
  And the suffix is a valid domain
  Then the email is valid
  And I see a message of "Email valid."

Scenario: Enter invalid email
  Given I have entered an email
  When the email is not valid
  Then I see a message of "Email invalid."

Scenario: Enter password
  When I enter a password
  Then the password is hidden as I type
  When the password is longer than 8 characters
  Then I see a message of "Password entered"

Scenario: submit form
  Given I have entered a valid email
  And I have entered a password
  When I select submit
  Then the form is submitted

Scenario: valid email and password
  Given I have entered a valid email
  And I have entered a matching password
  When the form is submitted
  Then I see a message of "Log in successful"

Scenario: invalid password
  Given I have entered an invalid password
  When I submit the form
  Then I see a message of "Password invalid"
  Then I see a link with text "Forgot your password?"

```

## Reset password

Story LOG-4 {: .ml-0 .mb-0 .label .label-green }

As a user, I want to reset my password, so that I recover access my account

```
Scenario: navigate to recovery
  Given I am not logged in
  When I navigate to the log in screen
  Then I see a link with text "Forgot your password?"
  When I click the link
  Then I navigate to reset my password

Scenario: Submit recovery form
  When I navigate to reset my password
  Then I see a form field labelled email
  And a button with text "Submit"
  And I see a message of "Submit your email to reset your password."
  When I enter an email
  And the email is valid
  And I submit the form
  Then the I see a message "Check your email for instructions."

Scenario: Receive email
  Given I have submitted the recovery form
  When I receive an email
  Then I see email text of "click the reset link to reset your password"
  And the email contains a reset link
  When I click the reset link
  Then I am directed to the application

Scenario: Set a new password
  Given I have received the recovery email
  And clicked the reset link
  When I am directed to the application
  Then I see a recovery form
  And I see a form field labelled "Password"
  And I see a button labelled "Submit"
  When I enter a new password
  Then I am able to submit the form
  When submit the form
  Then I am directed to log in

```
