% Code Quality
% Andi, Christopher
% 2021-05-19

# Getting Started Experience

## Documentation


- On the frontpage
- Graphical overview
- Provide all information for getting started
- Introduce workflows and tools
    - (Insomnia, Postman etc.)
- Document (possibly) unexpected behavior


## Case Study Crawlers

- Introduction in Wiki (easy to miss)
- What value is suitable as `sourceId`?
- `remove_namespaces()` in `parse()`
    - Selectors that worked in Scrapy shell don't work in code

## Configuration

- Provide ready-to-use configuration
    - Docker images + commands / `docker-compose.yml`
    - IDE configuration
    - CI/CD

## Case Study Crawlers

- Not-executable code due to old Python version
- CI/CD is missing configuration when forked

## Test

- Contracts / assertions
- Unit test
- End-to-end test

# Code

## Abstraction

- Be mindful when to use abstraction
    - Abstraction has a cost
    - Simplicity might be more valuable than structure
- Abstraction without encapsulation
    - imposes complexity
    - fails to improve structure

## Case Study Crawlers

- Class structure makes assumptions about scraped pages:
    - One item per page
- Inheritance structure makes it hard to see where and when things happen
- The developer has to keep track of many files for accomplishing simple tasks

## Coding Manners

- Give the developer tools
- Don't force them to deal with X
- Provide meaningful error messages
    - Even for developer mistakes

## Case Study Crawlers

- Edu-sharing configuration is mandatory
    - Time-consuming debugging
- Edu-sharing connection is mandatory
    - use-case for a "proper" offline-mode 
    (since "json"-mode is still "online")

## Code Hygiene

- Don't rely on side effects

## Code Style

- Use auto formatters and linters

## Case Study Crawlers

- `sourceId` vs `sourceID`

## In-code Documentation

- Type hints
- Docstrings / doc comments