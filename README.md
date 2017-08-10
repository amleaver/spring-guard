# Spring Guard

A tiny project with a very simple [Guard](https://github.com/guard/guard) configuration for watching
Ruby files within a project and kills any running Spring processes should a non-test Ruby file change.

This works around an issue with a particular problem wherein Spring needed to be restarted if an application
file changed, but not for test files.

## Usage

`bundle exec guard -w /path/to/rails/project`

Note that relative paths also work.

Setting `export SPRING_GUARD_DEBUG=true` will enable debug logging where all file changes are logged,
not just those which are non-test Ruby files.
