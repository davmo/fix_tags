# fix_tags

A Perl script to manipulate tags on a variety of audio file types.

Requires the following Perl modules:

- `Modern::Perl`
- `Getopt::Long`
- `Pod::Usage`
- `Data::Dumper`
- `File::stat`
- `File::Temp`
- `File::Slurp`
- `Date::Manip::Delta`
- `Date::Manip::TZ`
- `Audio::TagLib`
- `TryCatch`
- `HTML::Restrict`

Installing Audio::TagLib might be problematic and seems to require the
prior installation of the TagLib package (libtag1-dev on Debian).

### Update 2016-12-09

It looks as if `Audio::TagLib` has vanished from the CPAN repository. It is
not clear why, although the module has apparently not been actively maintained
for some time. Looking at the equivalent interface libraries for Python and
Ruby, neither have they. This in itself does not seem to be a reason to drop
it, since the TagLib API hasn't changed to my knowledge.

The module can still be downloaded and installed thus:

    $ wget http://search.cpan.org/CPAN/authors/id/G/GL/GLEACH/Audio-TagLib-1.65.tar.gz
    $ tar -xvzf Audio-TagLib-1.65.tar.gz
    $ cd Audio-TagLib-1.65/
    $ perl Makefile.PL
    $ make
    $ make test    # should get the result 'PASS'
    $ sudo make install

### Update 2019-06-26

As of today (and for some time probably) `Audio::TagLib` is back in CPAN. The
current version is 1.67.

Created `fix_tags.bin`, which is a binary version of `fix_tags` which can run
stand-alone. It is not a container, just the encapsulation of the Perl script
as a binary. It's slow to start, but does actually work, and is a way of
avoiding having to install and build all the components listed above.

### Update 2019-07-14

I should have noted how I created `fix_tags.bin`. I used the module called
`'pp\ -\ PAR Packager'` which is documented online at
https://metacpan.org/pod/pp. I used the `pp` command it provides to bundle
everything into a single binary file with the command:

    $ pp -o fix_tags.bin fix_tags

### Documentation

The script is intended to be self-documenting. Run:

    fix_tags -help

for basic help, or use `perldoc` in this way (against the Perl script, not the
binary file):

    perldoc -oman /path/to/fix_tags

to obtain the full help in Man format.

To create a PDF version of the documentation:

    pod2pdf /path/to/fix_tags --out=fix_tags.pdf

Where `pod2pdf` comes from `App::pod2pdf`


<!--
vim: syntax=markdown:ts=8:sw=4:ai:et:tw=78:fo=tcqn:fdm=marker
-->
