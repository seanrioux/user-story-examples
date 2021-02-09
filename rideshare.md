---
layout: default
title: Rideshare user story example
permalink: /examples/rideshare
nav_order: 2
---

# Rideshare user story examples

An example ride-sharing experience from the perspective of a commuter who provides their location, and is connected to drivers in their area to successfully arrives at work on time. {: .fs-6 }

# Backlog

| ID | Summary | Description | Epic |
| --- | --- | --- | --- |
| RS-1 | Authorize my location | As a commuter, I want to authorize my location, so that I can get picked up nearby | Hail a ride |
| RS-2 | Enter my destination address | As a commuter, I want to enter my destination, so that I can plan my ride | Hail a ride |
| RS-3 | Confirm my estimated price | As a commuter, I want to confirm my estimated ride cost, so that I can book my ride | Hail a ride |
| RS-4 | View my ride on a map | As a commuter, I want to view my ride on a map, so that I can follow my drivers route | Hail a ride |
| RS-5 | View my arrival time | As a commuter, I want to view my time of arrival, so that I can ensure I'll be on time | Hail a ride |
| RS-6 | Rate my ride | As a commuter, I want to rate my ride, so that I can provide feedback on my experience | Hail a ride |
| RS-7 | Tip my driver | As a commuter, I want to tip my driver, so that I can thank them for my ride | Hail a ride |
| RS-8 | Confirmation of payment | As a commuter, I want to receive confirmation of payment, so that I can assess my total cost | Hail a ride |

# Stories and Acceptance Criteria

## Hail a ride

Epic {: .ml-0 .mb-0 .label .label-purple }

As a commuter, I want to hail a rides, so that I can commute to work

## Authorize my location

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to authorize my location, so that I can get picked up nearby {: .fs-4 }

```
Feature: Location

  Background:
    Given I have registered
    * I have entered payment details
    * I open the app
    * I am logged in
    * I am on the map screen

  Scenario: Receive location prompt
    Given I have not authorized my location
    And it is my first login
    Then I see a "Share my location" prompt
    And I see a button to "Confirm"
    And I see a button to "Cancel"

  Scenario: Confirm location prompt
    Given I see a "Share my location" prompt
    When I select the button to "Confirm"
    Then location sharing is authorized
    And the "Share my location" prompt is closed
    And I can see my current location

  Scenario: Cancel location prompt
    Given I see a "Share my location" prompt
    When I select the button to "Cancel"
    Then location sharing is not authorized
    And the "Share my location" prompt is closed
    And I cannot see my current location

  Scenario: Trigger location prompt
    Given I have not authorized my location
    Then I see a "Authorize my location" link
    When I click the "Authorize my location" link
    Then I see the "Share my location" prompt

```

## Enter my destination address

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to enter my destination, so that I can plan my ride {: .fs-4 }

```
Feature: Destination

  Background:
    Given I have registered
    * I have entered payment details
    * I open the app
    * I am logged in
    * I am on the map screen

  Scenario: Cannot enter destination address
    Given I have not authorized location
    Then I see a "Destination" input
    And the "Destination" input is disabled
    And I am unable to view my location
    And I see a "Authorize my location" link

  Scenario: Enter destination address
    Given I have authorized location
    Then I see a "Destination" input
    When I enter an address into the "Destination" input
    Then I see a destinations list

  Scenario: Select destination
    Given I have entered a destination address
    When I select my destination from the destinations list
    Then I see a "Confirm my destination" prompt
    And I see a button to "Confirm"
    And I see a button to "Cancel"

  Scenario: Confirm destination
    Given I see a "Confirm my destination" prompt
    When I select the button to "Confirm"
    Then my destination is confirmed
    And the "Confirm my destination" prompt is closed

  Scenario: Cancel destination
    Given I see a "Confirm my destination" prompt
    When I select the button to "Cancel"
    Then my destination is cancelled
    And the "Confirm my destination" prompt is closed
```

## Confirm my estimated price

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to confirm my estimated ride cost, so that I can book my ride {: .fs-4 }

```

Feature: Estimated price

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in
    * I am on the map screen
    * I have authorized my location

  Scenario: View estimated cost
    When I have confirmed my destination
    Then I see an "Confirm estimated price" prompt
    And I see an estimated cost range
    And I see a button to "Confirm"
    And I see a button to "Cancel"

  Scenario: Confirm ride
    Given I see the "Confirm estimated price" prompt
    When I select the button to "Confirm"
    Then my ride is confirmed
    And the "Confirm estimated price" prompt is closed

  Scenario: Cancel ride
    Given I see the "Confirm estimated price" prompt
    When I select the button to "Cancel"
    Then my ride is cancelled
    And the "Confirm estimated price" prompt is closed

```

## View my ride on a map

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to view my ride on a map, so that I can follow my drivers route {: .fs-4 }

```
Feature: Map

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in

  Scenario: View map
    Given I have authorized my location
    When I am on the map screen
    Then I can see a map
    And I can see rides nearby

  Scenario: View map
    Given I have not authorize my location
    When I am on the map screen
    Then the map is disabled

  Scenario: View driver on map
    Given I have confirmed a ride
    But I have not begun my trip
    When I see the map
    Then I can see my drivers location

  Scenario: View route
    Given I have begun my trip
    When I see the map
    Then I can see my location
    And I can see my drivers route
```

## View my arrival time

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to view my time of arrival, so that I can ensure I'll be on time {: .fs-4 }

```
Feature: Arrival time

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in
    * I have authorized location
    * I have entered a destination
    * I have confirmed a ride

  Scenario: View estimated arrival time
    Given I have begun my trip
    When I view the map
    Then I can see my estimated arrival time

  Scenario: Receive notice of arrival
    When I arrive at my destination
    Then I receive a "You have arrived" notification
    When I view the notification
    Then I see my final arrival time
```

## Rate my ride

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to rate my ride, so that I can provide feedback on my experience {: .fs-4 }

```
Feature: Rate ride

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in
    * I have authorized location
    * I have entered a destination
    * I have confirmed a ride

  Scenario: View rating prompt
    Given I have arrived at my destination
    When I view to the "You have arrived" notification
    Then I see a "Rate my ride" prompt
    And I see rating options from 0 to 5 stars
    And 5 stars is selected
    And I see a button to "Confirm"
    And I see a button to "Cancel"

  Scenario: Select and confirm rating
    When a rating is selected
    And I select the button to "Confirm"
    Then my rating is submitted
    And the "Rate my ride" prompt is closed

  Scenario: Cancel rating
    When I select the button to "Cancel"
    Then the rating prompt is dismissed
    And no rating is submitted
    And the "Rate my ride" prompt is closed

```

## Tip my driver

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to tip my driver, so that I can thank them for my ride {: .fs-4 }

```
Feature: Tip driver

Feature: Rate ride

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in
    * I have authorized location
    * I have entered a destination
    * I have confirmed a ride
    * I have arrived

  Scenario: View tip prompt
    Given I have submitted a rating
    When the "Rate my ride" prompt is closed
    Then I see a "Tip my driver" prompt
    * I see a "Tip amount" input
    * I see "Tip percentage" options for "10%", "15%", and "18%"
    * I see a button to "Confirm"
    * The "Confirm" button is disabled
    * I see a button to "Cancel"

  Scenario: Submit tip percentage
    Given I see a "Tip my driver" prompt
    When I select a "Tip percentage" option
    Then I see a "Tip amount" as the selected percentage of my total cost
    Then I am able to select "Confirm"
    When I select "Confirm"
    Then my tip is submitted
    And the "Tip my driver" input is closed

  Scenario: Submit tip amount
    Given I see a "Tip my driver" prompt
    When I enter a number into the "Tip amount"
    Then I am able to select "Confirm"
    When I select "Confirm"
    Then my tip is submitted
    And the "Tip my driver" input is closed

  Scenario: Cancel tip prompt
    Given I see a "Tip my driver" prompt
    When I select "Cancel"
    Then no tip is submitted
    And the "Tip my driver" input is closed
```

## Confirmation of payment

Story {: .ml-0 .mb-0 .label .label-green }

As a commuter, I want to receive confirmation of payment, so that I can assess my total cost {: .fs-4 }

```
Feature: Receive payment confirmation

  Background:
    Given I have registered
    * I have entered payment details
    * I have opened the app
    * I am logged in
    * I have authorized location
    * I have entered a destination
    * I have confirmed a ride
    * I have arrived

  Scenario: Receive notification of payment
    When I have completed my trip
    Then I receive a email receipt
    When I view to email receipt
    Then I see my final total

  Scenario: See tip line item
    Given I have submitted a tip
    When I receive my email receipt
    Then my final total includes a "Tip" line item
    And my tip amount is added to the total

```
