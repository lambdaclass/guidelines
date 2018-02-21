# Guidelines
Design and coding standards for LambdaClass.

This will be quick and dirty list for now.

## Generalities

* make is the build tool
* postgresql is the default database
* Write tests
* Favor integration tests over unit tests, but do write unit tests
  when the functions merit them
* Start with [the simplest thing that could possibly work](http://www.artima.com/intv/simplest3.html).

## Open source projects

* Use MIT license
* Fill the `description` field at the top of the repo page
* Write a decent README
* A good readme starts with a succint description (one or two sentences) and, when possible, a very short and illustrative example use. The rest of the details go after this header.
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

