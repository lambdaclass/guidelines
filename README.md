# Guidelines
Design and coding standards for LambdaClass.

This will be quick and dirty list for now.

## Generalities

* make is the build tool
* postgresql is the default database
* Write tests
* Favor integration tests over unit tests, but do write unit tests
  when the functions merit them
* Do not write tests, at least until you have the problem solved,
  you may lost time writing test for a solution that don't resolve
  the problem.
* Early optimization is the root of all evil. First resolve the problem,
  the only if, and only if is needed optimize the solution.
* Start with [the simplest thing that could possibly work](http://www.artima.com/intv/simplest3.html).
* Write for humans: Coding for computers is easy, but writing
  code that is understandable by other person in an art.
* The less code you have the better. Deleted code is debugged code.
* Always lock your dependencies.
* Pin a specific version and a commit of a dependency, don't use the version at master.
* If you want to update a dependency, test it first.

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
* Avoid using header files (.hrl) [TODO ELABORATE]
* Supervised processes provide guarantees in their initialization phase, not a best effort. [If you expect failure to happen on an external service, do not make its presence a guarantee of your system](https://ferd.ca/it-s-about-the-guarantees.html).
* Try to avoid `timer:sleep` on tests, [ktn_task:wait_for_success](https://github.com/lambdaclass/erlang-katana/blob/master/src/ktn_task.erl#L28) can be a better option.
* Prefer maps to records.
