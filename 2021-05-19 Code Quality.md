% Code Quality
% Andi, Christopher
% 2021-05-19

# Getting Started Experience

## Documentation


- On the frontpage
- Graphical overview
- Provide all information for getting started
- Introduce workflows and tools (Insomnia, Postman etc.)
- Document (possibly) unexpected behavior


## Case Study Crawlers

- Introduction in Wiki (easy to miss)
- What value is suitable as `sourceId`?
- Selectors that worked in Scrapy shell don't work in code
    - `remove_namespaces()` in `parse()`

## Configuration

- Provide ready-to-use configuration
    - Docker images + commands / `docker-compose.yml`
    - IDE configuration (=> debug-config)
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

- Class structure makes assumptions about scraped pages
    - One item per page
    
        ```python
        def getId(self, response: scrapy.http.Response = None) -> str:
            raise NotImplementedError()
        ```

---

- Inheritance structure makes it hard to see where and when things happen
    - Overloads don't work the same in all languages (`*kwargs` / `**kwargs`)
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
    - use-case for a proper offline-mode 
    (since "json"-mode is still online)

## Code Hygiene

- Don't rely on side effects

## Code Style

- Use auto formatters and linters

## Case Study Crawlers

- `sourceId` vs `sourceID`

## In-code Documentation

- Type hints
- Docstrings / doc comments

# So long

## And thanks for all the fish

# Next Steps

## Documentation

- `Readme.md`
    - more inviting
    - more structure
    - link to GitHub wiki
    - short guide for configuration with Edu-Sharing Docker container
- extend the GitHub wiki 
    - redo the frontpage (short gists of what to expect within each wiki chapter), e.g.:
        - are you providing metadata? look at chapter X
        - do you want to build a crawler? take a peek at chapters Y & Z
    - help users understand the crawler-building-process with graphical illustrations
    - how to use LomBase for building spiders
    - more beginner guides (e.g. how to use Insomnia / Postman for building a crawler with API requests)
        - either by recommendation of well-suited tools for the task or giving a short-intro in the Wiki for our use-case

## Code
        
- provide an additional sample spider/template (similar to the Fobizz / -1 approach of building a crawler for easier readability)
- offline-mode for debugging / testing (no edu-sharing)
    - provide a ready-to-use docker-image
- extend Type Hints / DocStrings
- warn/fail for incompatible Python version
    ```python
    MIN_PYTHON = (2, 6)
    if sys.version_info < MIN_PYTHON:
        sys.exit("Python %s.%s or later is required.\n" % MIN_PYTHON)
    ```

## Tooling

- lint and format code
    - check in CI
- cleanup CI
- provide debug-configurations for VSCode / pyCharm 

## Tests

- use contracts for early fails / better error messages
    - https://docs.scrapy.org/en/latest/topics/contracts.html
    

# Next Next Steps

## Code

- reevaluate / refactor item-loader class structure