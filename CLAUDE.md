# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

The goal of this project is a simple command line application written in Python that can take a markdown file and put a line feed at the end of each sentence within a paragraph. The goal is to convert markdown text for more easily diffing the file using git.  

First, a set of test cases should be generated using the pytest framework.  They should include:

- A markdown file with regular paragraphs with 5 sentences that are separated by single spaces.
    - result: 5 separate lines containing containing the sentences.
- A markdown file with regular paragraphs with multiple sentences that are separated by double spaces.
    - result: 5 separate lines containing containing the sentences.
- A markdown file with regular paragraphs with 5 sentences that are separated by single spaces, where one of the sentences includes an ellipse.
    - result: 5 separate lines containing containing the sentences; the ellipse should not be modified. 

If you can think of any other edge cases where a period might occur within a sentence, generate tests for those as well.

Then, develop a module in python that can pass all of the tests.

Then, develop a command line interface that allows a user to pass in a file for processing. By default, the application should return the modified text to standard output.  If the -w flag is passed, then the file should be overwritten in place, after copying the original to a file with the .bak suffix.  If the -n flag is passed, then do not create the backup file before overwriting.

## Development Environment

The project has Claude Code configured with custom permissions in `.claude/settings.local.json`.

Development preferences:

- The project is managed using uv.  Any necessary imports should be added using `uv add` and tests should be run within the virtual environment that can be activated using .venv/bin/activate
- Do not include code in __init__.py files.
- Use pytest for testing.
- Write code that is clean and modular.  Prefer shorter functions/methods over longer ones.
- Create code that will work in Python 3.13 or later