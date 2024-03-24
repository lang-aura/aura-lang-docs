# Project Structure

Aura projects are structured like this:
```
| aura.toml
| src/
| test/
| build/
```

The Aura CLI will construct the required project structure for you when you run the command `aura new <proj_name>`. The
resulting project will also contain an optional `README.md` in the project's root directory.

## `aura.toml`

This is the project's configuration file, and is used by the Aura CLI both as a marker of the project's root directory and
to extract information about the Aura project. The `aura new` command will produce a basic `aura.toml` file containing only
three keys:

```
[project]
name = <project_name>
version = "0.0.1"
description = ""
```

For a complete list of supported configuration keys, see [Configuration Keys](Configuration-Keys.md)

## `src/`

This directory contains the project's Aura source code. The `aura new` command will add a single source file to this
directory called `<project_name>.aura`, which will contain a simple Hello World program. Each directory under the `src/`
directory is considered its own module, and all source files in that directory must be a part of the same module (as identified
by the `mod` declaration at the top of the source file).

To understand how to import local modules into other Aura source file, see [Imports](Imports.md)

## `test/`

This directory contains the project's tests. Currently, Aura does not support a test framework, so this directory is empty
after running `aura new`.

## `build/`

This directory contains the project's build files produced by running `aura build`, as well as the Aura standard library
and prelude. This directory should not be manually updated by the programmer.