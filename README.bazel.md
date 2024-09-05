# Bazel workflows

This repository uses [Aspect Workflows](https://aspect.build) to provide an excellent Bazel developer experience.

## Linting code

We use [rules_lint](https://github.com/aspect-build/rules_lint) to run linting tools using Bazel's aspects feature.
Linters produce report files, which are cached like any other Bazel actions.
Printing the report files to the terminal can be done in a couple ways, as follows.

The [`lint` command](https://docs.aspect.build/cli/commands/aspect_lint) is provided by Aspect CLI but is *not* part of the Bazel CLI provided by Google.
It collects the correct report files, presents them with nice colored boundaries, gives you interactive suggestions to apply fixes, produces a matching exit code, and more.

- Run `aspect lint //...` to check for lint violations.

## Installing dev tools

For developers to be able to run a CLI tool without needing manual installation:

1. Add the tool to `tools/tools.lock.json`
2. `cd tools; ln -s _multitool_run_under_cwd.sh name_of_tool`
3. Instruct developers to run `./tools/name_of_tool` rather than install that tool on their machine.

See https://blog.aspect.build/run-tools-installed-by-bazel for details.








