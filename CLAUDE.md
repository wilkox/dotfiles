# General instructions

- YOU MUST ALWAYS address me as "David" in all communications
- EVERY part of a project - code, comments, features, examples, documentation - is there intentionally
- NEVER remove code, comments, features, examples, documentation, or anything else just because you don't understand it
- NEVER remove code, comments, features, examples, documentation, or anything else because something isn't working and removing it is easier than fixing it
- YOU MUST NEVER remove code comments unless you can PROVE they are actively false. Comments are important documentation and must be preserved
- YOU MUST NEVER throw away implementations to rewrite them without EXPLICIT permission. If you're considering this, YOU MUST STOP and ask first.
- YOU MUST NOT change whitespace unrelated to code you're modifying.
- We STRONGLY prefer simple, clean, maintainable solutions over clever or complex ones. Readability and maintainability are PRIMARY CONCERNS, even at the cost of conciseness or performance
- YOU MUST make the SMALLEST reasonable changes to achieve the desired outcome
- YOU MUST MATCH the style and formatting of surrounding code, even if it differs from standard style guides. Consistency within a file trumps external standards
- YOU MUST NEVER make code changes unrelated to your current task. If you notice something that should be fixed but is unrelated, document it rather than fixing it immediately
- YOU MUST NEVER refer to temporal context in comments (like "recently refactored"). Comments should be evergreen and describe the code as it is
- YOU MUST NEVER use temporal naming conventions like 'improved', 'new', or 'enhanced'. All naming should be evergreen
- YOU MUST NEVER implement mock modes for testing or any purpose. We always use real data and real APIs

# Version control

- Version control is with git
- If the project isn't in a git repo, YOU MUST STOP and ask permission to initialize one
- ALL changes MUST be tracked in git
- YOU MUST commit frequently throughout the development process
- If there are uncommitted changes or untracked files when starting work, YOU MUST STOP and ask how to handle them. Suggest committing existing work first
- When starting work without a clear branch for the current task, YOU MUST create a WIP branch.
- ALWAYS run `git status` prior to committing to check the current status of the checkout and think about what files need to be included and excluded in the commit
- ALWAYS clean up any junk files (e.g. files created during testing) before committing, even if those files are not going to be committed. Commits should be clean, atomic snapshots
- Commit messages MUST be concise and describe only what has changed, not future plans
- The first line of a commit message MUST be a concise summary of what the commit does. This can be followed by bullet points describing each change in more detail
- All commits MUST include Claude as a co-author using the format: `Co-authored-by: Claude <noreply@anthropic.com>`

# Getting help

- YOU MUST ALWAYS ask for clarification rather than making assumptions
- If you're having trouble, YOU MUST STOP and ask for help, especially for tasks where human input would be valuable

# Testing

- Tests MUST comprehensively cover ALL implemented functionality
- YOU MUST NEVER ignore system or test output - logs and messages often contain CRITICAL information.
- Test output MUST BE PRISTINE TO PASS
- If logs or outputs are expected to contain errors, these MUST be captured and tested.
- NO EXCEPTIONS POLICY: ALL projects MUST have unit tests, integration tests, AND end-to-end tests. The only way to skip any test type is if David EXPLICITLY states: "I AUTHORISE YOU TO SKIP WRITING TESTS THIS TIME."

# Style guide

- Always use a space between numbers and units, e.g. "4 mm" not "4mm"
- Always use Australian English, e.g. "standardise" instead of "standardize"

# R packages

## Development cycle

- You will be given a plan, often written in an external file like plan.md
- Before starting work on a plan, YOU MUST check out a new development branch from master if not already in one
- YOU MUST work through the plan step by step, with each atomic element of the plan being committed before moving on
- For each step, YOU MUST write a failing test that defines the desired functionality BEFORE writing implementation code
- YOU MUST run the test to confirm it fails as expected
- YOU MUST write ONLY enough code to make the failing test pass
- YOU MUST run the test to confirm success
- YOU MUST refactor code while ensuring tests remain green
- YOU MUST repeat this process for each step
- Once the plan has been fully implemented, YOU MUST merge master back into the development branch and resolve any merging issues
- YOU MUST then increment the development version and merge the development branch back into master

## Development tools

- ALWAYS use tools from the tidyverse and r-lib
- ALWAYS use `devtools` and `usethis` for package-related operations. For example:
  - NEVER use `library()` to load the development version, ALWAYS use `devtools::load_all()`
  - NEVER create a NEWS.md yourself, ALWAYS run `usethis::use_news_md()`
  - NEVER manually implement version numbers, ALWAYS use `usethis::use_version()`
- Testing is ALWAYS with `testthis`, and visual testing (if used) is with `vdiffr`
- Documentation is ALWAYS with `roxygen2`
- Validation (e.g of arguments) is ALWAYS with `checkmate`, usually `checkmate::qtest()`
- Console output (errors, warnings, messages) is ALWAYS with `cli`

## READMEs

- R packages use README.Rmd as the primary README file
- ALWAYS edit README.Rmd rather than README.md
- ALWAYS complile README.md (and a local HTML preview, README.html) with `rmarkdown::render("README.Rmd")`
- ALWAYS open code blocks in README.Rmd and other Rmarkdown files with ```{r} to support syntax highlighting

## Testing and checking

- ALWAYS run tests with `devtools::test()`
- If running tests from a single file, ALWAYS use `devtools::test(filter = "keyword")`
- Tests should NEVER print any errors, warnings, or messages to the console during testing. ALWAYS Capture and redirect it with functions like `capture.output()`
- ALWAYS use `devtools::check()` to run R CMD check
- NEVER ignore NOTEs and WARNINGs from `devtools::check()`
- If you are unsure how to fix any failing tests or checks, YOU MUST STOP and discuss the problem with me before proceeding

## Preparing a commit

- YOU MUST check that NEWS.md has been updated to reflect any changes
- YOU MUST check that README.Rmd has been updated to reflect any changes
- YOU MUST re-compile README.Rmd
- YOU MUST run `git status` and clean up any junk files e.g. Rplots.pdf
- YOU MUST run tests with `devtools::test()` and fix any failing tests
- YOU MUST run R CMD check with `devtools::check()` and fix any issues, including updating the spellfile if needed
- YOU MUST read all documentation and fix poor or unclear writing, spelling or grammar issues, or other errors
- YOU MUST update documentation with `devtools::document()`
- YOU MUST REPEAT **ALL** OF THE ABOVE STEPS UNTIL THERE ARE NO NEW ISSUES
- YOU MUST then prepare a commit message for my approval

# Compliance Check

- Before submitting any work, verify that you have followed ALL guidelines above. If you find yourself considering an exception to ANY rule, YOU MUST STOP and get explicit permission from David first
