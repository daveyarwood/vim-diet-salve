# vim-diet-salve

Tim Pope's original [vim-salve][salve] plugin provides static Vim support for
[Leiningen][lein] and [Boot][boot].

> Leiningen ran... [the ants] would get to him soon, despite the salve on
> his boots.

-- from "Leiningen versus the Ants"

One of the features of vim-salve is that it seeds Vim's `path` with the JVM
classpath in order to enable certain behaviors such as determining the location
of your source code for navigation commands, etc.

Unfortunately, as a consequence (and out of necessity for the features it
provides), there is a noticeable delay of several seconds or more when
starting Vim; this happens the first time you open Vim in a particular
Clojure project directory, and then each time the project manifest file changes
(e.g. `project.clj` or `build.boot`, or `~/.lein/profiles.clj` or
`~/.boot/profile.boot`).

You might view this as an acceptable trade-off for some of the features of
vim-salve that having Vim's `path` seeded with the classpath enables. If that's
true for you, then you should use vim-salve.

If you're like me, you find the frequent disruption of long Vim startup times to
be more cumbersome than the classpath-aware features are worth. But maybe there
are some features of vim-salve that you still want to utilize, if possible,
without enduring the long Vim startup times. If this piques your interest, then
read on!

## Features

* `:Console` command to start a REPL or focus an existing instance if already
  running using [dispatch.vim][dispatch].

* Autoconnect [fireplace.vim][fireplace] to the REPL, or autostart it with
  `:Console`.

* Use `:make` to invoke `lein` or `boot`, complete with stacktrace parsing.

## What's missing?

vim-diet-salve is essentially vim-salve, but without the following aspects:

* Does not detect the classpath and use it to set Vim's `path`.

* Does not integrate with the [projectionist][] workflow.

Consequently, the following features of vim-salve are not supported:

* Source navigation commands:
  * `:Emain`, `:Esource`, `:Etest` and `:Eresource`
  * `:A` to alternate between test and implementation

* Support for `:find` and `gf`, which let you navigate to a file on Vim's
  `path`.

## Installation

Using your preferred method of installing Vim plugins, install the following
plugins:

```
daveyarwood/vim-diet-salve
tpope/vim-dispatch
tpope/vim-fireplace
```

Once help tags have been generated, you can view the manual with
`:help salve`.

## License

vim-diet-salve is a fork of [vim-salve][salve]; which is copyright © Tim Pope.
Distributed under the same terms as Vim itself. See `:help license`.

[salve]: https://github.com/tpope/vim-salve
[lein]: http://leiningen.org/
[boot]: http://boot-clj.com/
[projectionist]: https://github.com/tpope/vim-projectionist
[fireplace]: https://github.com/tpope/vim-fireplace
[dispatch]: https://github.com/tpope/vim-dispatch

