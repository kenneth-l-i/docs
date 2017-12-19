# Judge Configuration
The DMOJ judge is configured with a YAML file, which contains the runtimes, problems folders, and other information.

## Runtimes

The runtimes are configured with a `runtime` node. This can be automatically configured with `dmoj-autoconf`. As of writing, `dmoj-autoconf` is broken on Windows.

## Problems

The problems are configured with `problem_storage_root`. There are three ways to configure this node:

1. A single string: all grandchildren directories which include an `init.yml` will be treated as a problem directory.
2. A list: all children of each element in the list will be treated as a problem directory.
3. A dictionary: the key is an integer and the value is a string. The n-th level children of the string will be considered problem directories, where `n` is the entry's key.

## Id

The judge's display name is configured with an `id` node. This is a string, and it should match the one on the site interface.

## Key

This key is used to validate your judge's connection to the bridge, and as such, should match the one on the site interface. This is configured with a `key` node.

## Tempdir

A Windows-only entry, configured with a `tempdir` node, which specifies a temperary directory for the judge to use. See [this](https://github.com/DMOJ/docs/blob/master/docs/judge/windows_installation.md#very-important-note) for more information.
