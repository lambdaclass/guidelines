# Guidelines
Design and coding standards for LambdaClass.

This will be quick and dirty list for now.

## Generalities

* [make is the build tool](https://medium.com/@jlouis666/how-to-build-stable-systems-6fe9dcf32fc4#71e8). Consider [these notes](http://gromnitsky.users.sourceforge.net/articles/notes-for-new-make-users/).
* [Postgresql is the default database](https://medium.com/@jlouis666/how-to-build-stable-systems-6fe9dcf32fc4#e398).
* Write tests.
* Favor integration tests over unit tests, but do write unit tests
  when the functions merit them.
* Start with [the simplest thing that could possibly work](http://www.artima.com/intv/simplest3.html).
* Code and document in english, unless you have a very specific reason no to.
* Use meaningful, readable names for variables, functions and files. Don't try to save characters.
* Follow the [Zen of Python](https://www.python.org/dev/peps/pep-0020/), regardless of the language you are using at the moment. English also counts as a language.
* Use git and commit often, even on one-person projects.
* Documentation is a sign of the quality of an API. It's easier to write it when the design is right.
* Avoid the use of wrappers.

## Open source projects

* Use MIT license.
* Fill the `description` field at the top of the repo page.
* Write a decent README.
* A good readme starts with a succint description (one or two sentences) and, when possible, a very short and illustrative example use. The rest of the details go after this header.
* Use continuous integration, most likely travis.org.
* Don't introduce prematurely dependencies. You must evaluate your requirements, maintenance and integration costs first.
* Aim for simplicity, not performance. The latter is a by-product of the first.
* Make a good balance of features vs maintenance. Maintenance details usually matter more than adding a lot of features.

## Erlang projects

* Use rebar3. Include the binary in the repository so it's not an external dependency and the tested version is used. rebar3 is not used directly but through make targets.
* Support the most recent Erlang version.
* When building libraries, try to make them both easily usable from
  the shell and easily configurable via application environment.
* Indent with two spaces.
* Avoid using header files (.hrl) [TODO ELABORATE].
* Supervised processes provide guarantees in their initialization phase, not a best effort. [If you expect failure to happen on an external service, do not make its presence a guarantee of your system](https://ferd.ca/it-s-about-the-guarantees.html).
* Try to avoid `timer:sleep` on tests, [ktn_task:wait_for_success](https://github.com/lambdaclass/erlang-katana/blob/master/src/ktn_task.erl#L28) can be a better option. More on this [here](https://medium.com/erlang-battleground/the-missing-testing-tip-628686ebbbda).
* Prefer maps to records.

