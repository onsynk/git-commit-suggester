---
name: git-commit-suggester
description: Analyze unstaged or current Git changes and suggest professional, convention-compliant commit messages. Use when the user asks for commit message suggestions, help with git commit, or review of git diff for uncommitted changes.
---

# Git Commit Suggester

A skill to analyze code changes (`git diff`) that have not yet been committed and generate clear, concise, and conventional commit messages following the Conventional Commits specification.

## When to Use

- The user wants a commit message for current uncommitted changes.
- The user asks to review `git diff` / `git status` for files that have not yet been committed.

## Workflow

1. **Inspect Changes**:
   - Run `git status` to see modified, added, or deleted files that are not committed.
   - Run `git diff` to examine the exact modifications of unstaged files. (Can also check `git diff --cached` if requested, but focus primarily on uncommitted changes).

2. **Categorize the Change Type**:
   - `feat`: A new feature
   - `fix`: A bug fix
   - `docs`: Documentation only changes
   - `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.)
   - `refactor`: A code change that neither fixes a bug nor adds a feature
   - `perf`: A code change that improves performance
   - `test`: Adding missing tests or correcting existing tests
   - `chore`: Changes to the build process or auxiliary tools and libraries

3. **Formulate the Commit Message**:
   - Follow the Conventional Commits format: `<type>(<scope>): <short description>`
   - Keep the first line under 50 characters, using the imperative mood (e.g., "add" instead of "added" or "adds").
   - Add an optional body if the change is complex, explaining _what_ and _why_ (not _how_).

4. **Present Options**:
   - Provide 2 to 3 tailored options (e.g., concise, detailed, or alternative scopes) so the user can choose the best fit.
   - Provide the exact copy-pasteable terminal command (e.g., `git commit -m "..."`).
