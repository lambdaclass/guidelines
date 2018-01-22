# Guidelines
Design and coding standards for LambdaClass.

This will be quick and dirty list for now.

## Generalities

* make is the build tool
* postgresql is the default database
* Write tests
* Favor integration tests over unit tests, but do write unit tests
  when the functions merit them

## Open source projects

* Use MIT license
* Write a decent README
* Use continuous integration, most likely travis.org

## Erlang projects

* Use rebar3. Include the binary in the repository so it's not an external dependency and the tested version is used. rebar3 is not used directly but through make targets.
* Support the most recent Erlang version
* When building libraries, try to make them both easily usable from
  the shell and easily configurable via application evnironment
* Indent with two spaces.
