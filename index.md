---
layout: default
title: Getting started with user stories
nav_order: 1
---

# User story examples

A free to use knowledge base to help you write better user stories.

## Getting Started

User stories provide a way to simply and plainly describe user action and intent when interacting with a system (typically a user inteface). In considering both the steps a user takes, and their motivations, in a narritive form we aim to empathize with our users while delivering a product or service.

To get started, we'll dig into the components of a strong user story, before providing you with a range of example user story backlogs to draw from.

- [Create A User Story](#create-a-user-story)
- [Write Acceptance Criteria](#elaborate-acceptance-criteria)
- [Build A Backlog](#build-a-backlog)

### Create A User Story

To create a user story, fill in the blanks:

As a `[actor]`, I want to `[interaction]`, so that I can `[objective]`

Or more precisely:

As a `[actor]` I want to `[action]` _an_ `[object]` so that I can `[action]` _an_ `[intent]`

Let's flesh that out a bit more:

#### Actor

The `actor` is the first person subject of the story, and may be defined by their role in a system e.g.:

- As a new visitor
- As a prospective customer
- As a customer

As infered above, an actor, may transition their role as the navigate a system, end to end (i.e., from prospective customer to customer).

#### Interaction

An interaction is an _action_ we engage with an _object_, i.e., an external interaction with a system.

An `action` is a verb describing a clear interaction with an external object (or objects) e.g.:

- View
- Select
- add to cart
- check-out

An `object` is any thing (or _collection_ of things) we might interact with e.g.:

- A selection of shirts
- A Shirt
- A shopping cart

An object can also include object _properties_ e.g., _shirt colour_, _shirt size_, etc.

If we put action and object together:

- I want to view a selection of shirts
- I want to select a shirt colour
- I want to select a shirt size
- I want to add a shirt to cart
- I want to check-out my cart

#### Objective

An `objective` is the intent of the interaction i.e., the _why_. An objective is also _action oriented_ however, it describes action towards internal motivations, rather then external interaction.

In this regard our objective `action` should use _goal oriented_ verbs, for example:

- Explore
- Continue
- Achieve
- Complete

Our `intent` of the story, similarly, should be _goal oriented_ and help the story to express the internal motivation of our actor i.e., the object of their desire e.g.:

- My preferences
- My options
- A new shirt

As you can see by the last example in the list, the object of their desire might be the same object of the interaction. This is ok; just remember that our aim is to empathize with a use so perhaps consider _why do they want a new shirt?_ e.g.. _to look fresh for my job interview_.

Let's put that together into some **objective examples**:

- so that I can explore my options
- so that I can match my preferences
- so that I can look fresh for my job interview

#### Examples

Ok, Lets put that _all_ together. Here are some examples:

- As a visitor, I want to view a selection of shirts, so that I can explore my options
- As a prospective customer, I want to select a shirt colour, so that I can match my preference
- As a customer, I want to purchase a shirt, so that I can look fresh for my job interview

On this site you'll find many more examples of user stories, just like this, that will walk through many different possible applied cases for user stories.

### Write Acceptance Criteria

You can also elaborate on your user stories (using the recommended [Gherkin syntax](https://cucumber.io/docs/gherkin/reference/)) to establish a detailed step by step description of each interaction, while maintaining our first persona narritive.

We call this _acceptance criteria_, as it provides a criteria for testing that a story is actionable by a user (hence _accepted_, or complete).

#### Gherkin

While a more complete breakdown of the [Gherkin syntax](https://cucumber.io/docs/gherkin/reference/) is beyond the scope of this site, here is a summary:

- Gkerkin is a syntax for writing interface specifications in plain, narritive, language
- Like user stories, follows a formula, with a set of simple keywords to outline steps
- Gherkin is predicated on the concept of [behaviour-driven development](https://cucumber.io/docs/bdd/) (or BDD), whereby behaviour defines our solutions (rather then _business logic_)
- Gherkin's BDD approach pairs well with user stories and it's _user-centricity_
- Not only is Gherkin a great standard model to apply to acceptance criteria it also offers possibility of test automation (connecting our design, development and testing processes )

**Here is an example**

As a visitor, I want to view a selection of shirts, so that I can explore available options

```
Scenario: Visit the store
  Given I am in the neighbourshood
  When I visit the store
  Then I find a selection of shirts

Scenario: explore the shirts by property
  When I view a selection of shirts
  Then I find shirts organized by colour
  And I find shirts organized by size
```

### Build A Backlog

As should be be clear in our examples, when designing a system (e.g., a product or service) we can create an ordered set of user stories to conceptualize an end-to-end user experience. This often described as a _backlog_.

While your backlog will likely live in your project management software, maintaining your user stories and acceptance criteria for the long term serves a essential documentation for your product.

In this regard we recommend establishing your backlog in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) first.

**Here is a template**

```



```

On this site you'll find more example backlogs organized by user experience. These will cover a range of typical use cases, e.g.:

- Ordering delivery
- Booking travel accomidation
- Purchasing an investment

We'll also provide additional resources to help you write your own user stories, acceptance criteria and how to organize your backlog or prioritize towards an MVP.
