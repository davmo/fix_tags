# fix_tags

A Perl script to manipulate tags on a variety of audio file types.

Requires the following Perl modules:

- Modern::Perl
- Getopt::Long
- Pod::Usage
- Data::Dumper
- File::stat
- File::Temp
- File::Slurp
- Date::Manip::Delta
- Date::Manip::TZ
- Audio::TagLib
- TryCatch
- HTML::Restrict

Installing Audio::TagLib might be problematic and seems to require the
prior installation of the TagLib package (libtag1-dev on Debian).

The script is intended to be self-documenting. Run:

    fix_tags -help

for basic help, or use `perldoc` in this way:

    perldoc -oman /path/to/fix_tags

to obtain the full help in Man format.

<!--
vim: syntax=markdown:ts=8:sw=4:ai:et:tw=78:fo=tcqn:fdm=marker
-->
