---
layout: default
title: Getting started
permalink: /
nav_order: 1
---

# User story examples

A free to use knowledge base to help you write better user stories.

[View on Github](https://github.com/seanrioux/user-story-examples){: .btn .btn-purple }

# Getting Started

User stories provide a way to simply and plainly describe user action and intent when interacting with a system (typically a user interface). In considering both the steps a user takes, and their motivations, in a narrative form we aim to empathize with our users while delivering a product or service.

To get started, we'll dig into the components of a strong user story, before providing you with a range of example user story backlogs to draw from.

- [User story examples](#user-story-examples)
- [Getting Started](#getting-started)
  - [Create A User Story](#create-a-user-story)
    - [Actor](#actor)
    - [Interaction](#interaction)
    - [Objective](#objective)
    - [User Story Examples](#user-story-examples-1)
  - [Write Acceptance Criteria](#write-acceptance-criteria)
    - [Gherkin](#gherkin)
    - [Acceptance Criteria Example](#acceptance-criteria-example)
  - [Build A Backlog](#build-a-backlog)
  - [Use This Resource](#use-this-resource)
  - [Other Resources](#other-resources)

## Create A User Story

To create a user story, fill in the blanks:

- As an `actor`, I want to `interact with something`, so that I can `achieve some objective`

Or more precisely:

- As a `actor` I want to `action object(s)` so that I can `action intent(s)`

Let's flesh that out a bit more:

### Actor

The `actor` is the first person subject of the story, and may be defined by their role in a system or their persona e.g.:

- A visitor
- A prospect
- A customer
- Susan

As inferred above, an actor may transition their role as the navigate a system, end to end (e.g., from visitor, to prospect, to customer).

### Interaction

An interaction is an _action_ we engage with an _object_, i.e., an external interaction with a system.

An `action` is a verb describing a clear interaction with an external object (or objects) e.g.:

- View
- Select
- Add
- Check-out

An `object` is any thing (or _collection_ of things) we might interact with e.g.:

- Shirts
- A Shirt
- A shopping cart

An object can also include object _properties_ e.g., _shirt colour_, _shirt size_, etc.

If we put action and object together:

- I want to view shirts
- I want to select a shirt colour
- I want to select a shirt size
- I want to add a shirt to cart
- I want to check-out my cart

### Objective

An `objective` is the intent of the interaction i.e., the _why_. An objective is also _action oriented_ however, it describes action towards internal goals, rather than external interaction.

In this regard our objective `action` should use _goal oriented_ verbs, e.g.,:

- Explore
- Continue
- Achieve
- Complete

Our `intent` of the story, similarly, should be _goal oriented_ and help the story to express the internal motivation of our actor i.e., the object of their desire e.g.:

- My preferences
- My options
- A new shirt

As you can see by the last example in the list, the object of their desire might be the same object of the interaction. This is ok; just remember that our aim is to empathize with a user so always consider, _why?_

Let's put that together into some objective examples:

- so that I can explore my options
- so that I can match my preferences
- so that I can look great

### User Story Examples

Ok, Let's put that _all_ together. Here are some examples:

- _As a visitor, I want to view a selection of shirts, so that I can explore my options_
- _As a prospective customer, I want to select a shirt colour, so that I can match my preference_
- _As a customer, I want to purchase a new shirt, so that I can look great for my job interview_

On this site you'll find many more examples of user stories, just like this, that will walk through many different possible applied cases for user stories.

## Write Acceptance Criteria

You can also elaborate on your user stories (using the recommended [Gherkin syntax](https://cucumber.io/docs/gherkin/reference/)) to establish a detailed step by step description of each interaction, while maintaining our first persona narrative.

We call this _acceptance criteria_, as it provides a criteria for testing that a story is actionable by a user (hence _accepted_, or complete).

### Gherkin

Gherkin is a syntax for writing specifications in a narrative way. Based on the concept of [behaviour-driven development](https://cucumber.io/docs/bdd/) (BDD), Gherkin, follows a formula, with standard keywords for describing interactions, e.g.,

- `Given` e.g., given some pre-condition i.e., used to introduce the pre-text
- `When` e.g., when an action is taken i.e., used to describe an action or process step
- `Then` e.g., then something occurs i.e., describes the effect of the action or step

These steps can also be chained together or modified using:

- `And`, e.g., And when, and then, and then
- `But`, e.g., But when this action, then this occurs

Gherkin also employs indentation, and special keywords to help organize interactions e.g.:

```
Feature: Add a shirt to cart

  Scenario: Select a shirt
    Given...
    When...
    Then...

  Scenario: etc.
```

As a standard Gherkins can be really powerful in helping to expand on your stories, and narrow your specifications. Thats not to mention, that it can be used [as the basis for end-to-end testing](https://cucumber.io/tools/cucumber-open/).

### Acceptance Criteria Example

Let's put that all together with a user story example from above:

_As a visitor, I want to view a selection of shirts, so that I can explore available options_

```
Feature: View a selection of shirts

  Scenario: Visit the store
    Given I am in the neighbourshood
    When I visit the store
    Then I find a selection of shirts

  Scenario: explore the shirts by property
    When I view a selection of shirts
    Then I find shirts organized by colour
    And I find shirts organized by size
```

## Build A Backlog

As should be be clear in our examples, when designing a system (e.g., a product or service) we can create an ordered set of user stories to conceptualize an _end-to-end user experience_.

This is often described as a _backlog_.

A good high level way to conceptualize your product backlog (even before writing stories) is to list, in order, all the interactions a user will take in a system.

**Here's an example**

1. Search for shirts
2. Find a selection of shirts
3. Browse by shirt category
4. Select a shirt
5. View shirt details
6. Select shirt colour
7. Add shirt to cart
8. Check-out my shirt
9. Receive my shirt

This works to provide a prompt to write a set of user stories, but also serves as an index of actions to model our product.

While your backlog will likely live in your project management software, maintaining your user stories and acceptance criteria for the long term serves as essential documentation for your product.

In this regard we recommend establishing your backlog in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) first.

**Here is a template**

```
# Product Name

A short yet terse description of your product.

## User stories

1. Find user story examples
2. Get started writing stories

### 1. Find user examples

As a product manager, I want to get started writing user stories, so that I can maintain more user centric specifications

`
Feature: Get started writing user stories

  Scenario: Read how to get started
    Given I have found User Story Examples
    When I view the home page
    Then I find 'Getting Started'
`
```

## Use This Resource

Here you'll find more example backlogs organized by user experience, and crafted as demonstrated in the Getting Started section.

These will cover a range of typical use cases, e.g.:

- Ordering delivery
- Booking travel accommodation
- Purchasing an investment

We'll also provide additional resources to help you write your own user stories, acceptance criteria and how to organize your backlog or prioritize towards an MVP.

[Let us know](mailto:sean@oyoboyo.com) if you find it helpful, or if you have any request or recommendations.

## Other Resources

- [ ] To do
