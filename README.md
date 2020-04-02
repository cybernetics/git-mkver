#  git-mkver

Helps version your software and patch version numbers into the build.

For more information head to the [project site](https://idc101.github.io/git-mkver/).

## Features

- Determine next version based on:
    - Last tagged commit
    - [Conventional Commits](https://www.conventionalcommits.org/)
    - Branch names
    - Manual tagging
- Next version conforms to [Semantic Versioning](https://semver.org/) scheme
- Patch the next version into the build:
    - Java
    - C#
    - Many others, fully configurable
- Tag the current commit with the next version

All of this can be configured based on the branch name so release/master branches get different
version numbers to develop or feature branches.

## Installation

Download the binary for your os from the [releases](https://github.com/idc101/git-mkver/releases) page and copy to somewhere on your path.


## Usage

Basic usage is to just call `git mkver next` and it will tell you the next
version of the software if you publish now.

```bash
$ git mkver next
v0.4.0
```

### Tagging

If you would like to publish a version, mkver can tag the current commit.

```bash
$ git mkver tag
```

This will apply an annotated tag from the `next` command to the current commit.

### Patching versions in files

If you would like to patch version numbers in files prior to building and tagging then
you can use the `patch` command. The files to be patched and the replacements are
defined in the `mkver.yaml` config file. A large number of standard patches come
pre-defined.

```bash
$ git mkver patch
```
