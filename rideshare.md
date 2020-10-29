---
layout: default
title: Rideshare
nav_order: 2
---

# Rideshare example

An example ride-sharing experience from the perspective of a commuter who provides their location, and is connected to drivers in their area to successfully arrives at their destination.

## User story index

1. Authorize my location
2. Enter my destinaion
3. Review pricing
4. Confirm
5. Follow
6. Ride
7. Arrive
8. Confirm
9. Rate

## Example user stories

### Enter my destination

As a commuter, I want to select my destination, so that I can book a ride to work

```
Feature: select my destination

  Scenario: Enter destination
    When I open the app
    And I am logged in
    Then I see a destination search
    When I enter my destination into the search
    Then I see a list of destinations

  Scenario: Selection destination
    Given I have searched destinations
    When I select a destination from the list of destinations
    Then I see a request for confirmation

  Scenario: Confirm my destination
    Given I have selected a destination
    When I confirm
    Then the app finds drivers
```

###

As a commuter, I want to authorize my location, so that I can find rides nearby

As a commuter, I want to view price, so that I can assess cost before I confirm my ride

As a commuter, I want to select to book, so that I can confirm my ride

As a commuter, I want to follow , so I can
