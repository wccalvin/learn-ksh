# Korn Shell Scripting Learning Plan

A progress tracker for *Learning the Korn Shell, 2nd Edition* by Arnold Robbins and Bill Rosenblatt, with practice aimed at understanding and writing ODT scripts.

Book: [O’Reilly table of contents](https://www.oreilly.com/library/view/learning-the-korn/0596001959/)

| Item | Notes |
| --- | --- |
| Operating system | macOS |
| ksh executable path | /bin/ksh |
| ksh version | version         sh (AT&T Research) 93u+ 2012-08-01 |

Timeline: four weeks, four sessions per week, 30–45 minutes per session. 

## Week 1: Shell Foundations

### Reading

- [ ] Chapter 1 — Korn Shell Basics: commands, arguments, and options.
- [ ] Chapter 1: filenames and wildcards.
- [ ] Chapter 1: standard input/output, redirection, and pipelines.
- [ ] Chapter 1: special characters and quoting.
- [ ] Chapter 3 — Customizing Your Environment: shell variables and quoting.
- [ ] Chapter 3: environment variables, `PATH`, and subprocess inheritance.

Skim shell history and background-job details on the first pass.

### Practice

- [ ] Write a script that accepts a filename and displays its contents.
- [ ] Try a filename containing spaces.
- [ ] Compare single quotes, double quotes, and unquoted variables.
- [ ] Redirect output to a file and pass output through a pipe.
- [ ] Compare sourcing a script with running it using `ksh`.

**Checkpoint:** Explain how a command receives arguments and why quoting matters.

## Week 2: Script Structure and Logic

### Reading

- [ ] Chapter 4 — Basic Shell Programming: scripts and functions.
- [ ] Chapter 4: positional parameters, including `$1`, `$#`, and `"$@"`.
- [ ] Chapter 4: basic string operators and command substitution.
- [ ] Chapter 5 — Flow Control: exit status and return values.
- [ ] Chapter 5: conditions, `if`/`else`, and file tests.
- [ ] Chapter 5: `case`, `for`, `while`, and `until`.
- [ ] Chapter 5: `break` and `continue`.
- [ ] Chapter 9 — Debugging Shell Programs: Basic Debugging Aids and Set Options.

Defer compound variables, namerefs, advanced pattern matching, and the advanced `pushd`/`popd` examples.

### Practice

- [ ] Add argument validation to the Week 1 script.
- [ ] Check whether the input file exists and is readable.
- [ ] Put a repeated operation into a function.
- [ ] Process multiple filenames with a loop.
- [ ] Return a success status on success and a nonzero status on failure.
- [ ] Check syntax and trace execution using the commands below.

**Checkpoint:** Write a small script with arguments, a function, a condition, and a loop without copying an example.

## Week 3: File Processing and Options

### Reading

- [ ] Chapter 7 — Input/Output and Command-Line Processing: I/O redirectors.
- [ ] Chapter 7: file descriptors and redirection order.
- [ ] Chapter 7: `printf`, `read`, and reading lines from files.
- [ ] Chapter 7: here-documents, substitution order, and quoting.
- [ ] Chapter 6 — Command-Line Options and Typed Variables: arithmetic.
- [ ] Chapter 6: `typeset` and local variables in functions.
- [ ] Chapter 6: indexed arrays; study associative arrays if supported by the target shell.
- [ ] Chapter 6: `shift` and `getopts`.

Defer `eval` and advanced formatting features.

### Practice

- [ ] Create a file containing dummy test names, one per line.
- [ ] Read and process each line, preserving spaces and backslashes.
- [ ] Write a summary containing processed, successful, and failed counts.
- [ ] Send error messages to standard error.
- [ ] Add a `-v` option for verbose output using `getopts`.
- [ ] Test empty input, missing input, and input containing spaces.

**Checkpoint:** Process a file and handle command-line options while keeping normal output and errors separate.

## Week 4: Reliability and ODT Script Review

### Reading

- [ ] Chapter 8 — Process Handling: subprocesses and subshells.
- [ ] Chapter 8: signals and `trap`.
- [ ] Chapter 8: `wait`, if the scripts start background work.
- [ ] Chapter 9: revisit basic debugging and tracing.

Defer coroutines, advanced parallelization, discipline functions, and the full debugger implementation.

### Practice

- [ ] Detect a failed command and report a useful error.
- [ ] Use `trap` to clean up a temporary file created by the practice script.
- [ ] Trace the script and explain the expanded commands.
- [ ] Select a small existing ODT script and explain each line.
- [ ] Recreate its basic logic using dummy commands and inputs.
- [ ] Document its inputs, environment dependencies, outputs, and failure behavior.

**Checkpoint:** Explain how a script behaves when a command fails or execution is interrupted.

## Useful Commands

```sh
ksh practice.sh      # Run using ksh
ksh -n practice.sh   # Check syntax without executing the script
ksh -x practice.sh   # Execute with tracing
```

Use the actual executable path if your target environment uses a specific ksh installation. A syntax check does not verify runtime behavior. Tracing can display expanded argument values, so practice with dummy data.

## Later Reading

- [ ] Chapter 2 — Command-Line Editing.
- [ ] Remaining sections of Chapter 3 — Customizing Your Environment.
- [ ] Advanced sections skipped in Chapters 4, 6, 7, 8, and 9, as needed.
- [ ] Chapter 10 — Korn Shell Administration.
- [ ] Appendix A — Related Shells, especially version differences relevant to the target environment.

Keep Appendix B — Reference Information handy throughout the plan.

## Session Log

For each topic: read an example, run it, change it, then recreate it without looking.

| Date | Reading / topic | Practice completed | What I learned / questions | Next step |
| --- | --- | --- | --- | --- |
| | | | | |

## Questions to Resolve

- [ ] <!-- Add a question here. -->

## ODT Script Review Template

Copy this section for each script reviewed. Record explanations rather than sensitive script contents.

### Script: `<name>`

- **Purpose:**
- **Interpreter / version:**
- **Arguments:**
- **Required environment variables:**
- **Input files:**
- **External commands / dependencies:**
- **Output files and messages:**
- **Exit statuses:**
- **Failure and cleanup behavior:**
- **Questions / unfamiliar syntax:**

- [ ] Explain every line.
- [ ] Recreate the core logic with dummy inputs.
- [ ] Try success and failure cases.

## Completion Checklist

- [ ] Understand quoting and argument expansion.
- [ ] Distinguish sourcing from executing a script.
- [ ] Use arguments, functions, conditions, and loops.
- [ ] Read files and redirect output and errors.
- [ ] Handle options and exit statuses.
- [ ] Check syntax and debug with tracing.
- [ ] Explain a representative ODT script and its failure behavior.

