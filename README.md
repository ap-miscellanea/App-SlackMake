# sm

SlackMake is a package creation helper for Slackware that tries to provide
sensible defaults for the conventional type of source tarball, but can also
cope with variations on the convention.

Nowadays, **most** Unix software is distributed…

1. as source tarball which extracts to a <code>frobnicator-<i>0.4.2</i></code>
   directory
3. containing C or C++ code
3. along with the `configure` program from GNU autoconf or something that
   tries to work much like it
4. i.e. which sets up a Makefile
5. which will contains an `install` target
6. which in turn respects a `DESTDIR` variable.

Occasionally a few of those assumptions do not hold, but usually most others
still will. In these cases, which is to say 98% of the time, all you need to do
to install this package as a via the Slackware package manager is this:

1. `sm cf` — to run `./configure` with many defaults
2. `sm` — to run `make` (saves two characters!)
3. <code>[fakeroot][] sm p</code> — to run `make install` and `makepkg` with
   many defaults
4. `sudo sm i` — to do `installpkg` with the package name given automatically

Each `sm` subcommand has many knobs to twiddle in order to change defaults
and other details. There are also several other subcommands. Consult `sm help`
to find out about everything.

Note that none of this is set in stone and most commands can be tweaked to do
things in very non-autoconf&make-like ways by adding switches: `sm` can create
packages out of just about everything if you hold its hand enough, though past
some point it becomes easier to do it by hand.

## Prerequisites

<tt>$ <b>[cpanm][] [App::Cmd][]</b></tt>

Eventually I want to split apart and then fatpack `sm` so it will require
nothing but `perl` itself.

[fakeroot]: http://fakeroot.alioth.debian.org/
[cpanm]: http://cpanmin.us/
[App::Cmd]: https://metacpan.org/module/App::Cmd
