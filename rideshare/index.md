---
layout: default
title: Rideshare user story example
nav_order: 2
---

# Rideshare user story example

An example ride-sharing experience from the perspective of a commuter who provides their location, and is connected to drivers in their area to successfully arrives at work on time.

## User story index

- [Authorize my location](#provide-my-location)
- [Select my destination](#select-my-destination)
- View estimated price
- Confirm price
- View my ride on a map
- View my time of arrival
- Learn about my driver
- Receive notice of arrival
- Receive notice of payment
- Rate my ride
- Tip my drive


## Example user stories

### Authorize location

As a commuter, I want to authorize my location, so that I can get picked up at nearby

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

### Enter destination address

As a commuter, I want to enter my destination address, so that I can plan my commute to work

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

### View estimated price

As a commuter, I want to view estimated price, so that I can consider my cost of commute

### Confirm price

As a commuter, I want to confirm price, so that I can book my ride to work

### View my ride on a map

As a commuter, I want to view my ride on a map, so that I can follow my route to work

### View my time of arrival

As a commuter, I want to view my time of arrival, so that I can ensure I'm on time

### View driver profile

As a commuter, I want to view my drivers profile, so that I can feel safe on my ride

### Notice of arrival

As a a commuter, I want to receive confirmation of arrival, so that I can assess my final travel time

### Notice of payment

As a commuter, I want to receive confirmation of payment, so that I can assess final cost on my arrival

### Rate my ride

As a commuter, I want to rate my ride, so that I can provide feedback on my experience

### Tip my driver

As a commuter, I want to tip my driver, so that I can thank them for my ride
