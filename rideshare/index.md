---
layout: default
title: Rideshare
nav_order: 2
---

# Rideshare example

An example ride-sharing experience from the perspective of a commuter who provides their location, and is connected to drivers in their area to successfully arrives at work on time.

## User story index

1. [Authorize my location](#provide-my-location)
2. [Select my destination](#select-my-destination)
3. View my ride on a map
4. Review pricing
5. Confirm
6. Follow
7. Ride
8. Arrive
9. Confirm
10. Rate

## Example user stories

### Authorize my location

As a commuter, I want to provide my location, so that I can find rides nearby

```
Feature: Authorize my location

  Scenario: Receive location authorization request
    When I open the app
    And I have not authorized the app to access my location
    Then I see a prompt to share my location

  Scenario: Confirm location authorization request
    Given I am prompted to authorize sharing my location
    When I confirm authorization
    Then I am able to select my destination
```

### Select my destination

As a commuter, I want to select my destination, so that I can book a ride to work

```
Feature: select my destination

  Scenario: Enter my destination address
    When I open the app
    And I am logged in
    And I have authorized my location
    Then I see a destination search input
    When I enter my work address into the search input
    Then I see a list of destinations

  Scenario: Select my destination from a list
    Given I have entered my work address
    When I select my work place from the list of destinations
    Then I see a prompt to confirm my selection

  Scenario: Confirm my selection
    Given I have selected a destination
    When I select confirm
    Then the app finds drivers near my location
```

###

As a commuter, I want to view price, so that I can assess cost before I confirm my ride

As a commuter, I want to select to book, so that I can confirm my ride

As a commuter, I want to follow , so I can
