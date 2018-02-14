# v0.2.2 - February 14th, 2018

* Fixed several bugs surrounding parsing of the network data. More replays are now parseable

## v0.2.1 - February 1st, 2018

* If a directory argument is provided, the top level is searched for any `*.replay` files. This works around issues when the shell
  expands the glob to too many files and makes it easier to work with on Windows (which does not expand globs).

## v0.2.0 - January 31st, 2018

* Process replays in parallel using the `-m` option
* Add rudimentary network data parser. Since it's not surefire, it's not enabled by default.
* Support an older replay format

## v0.1.0 - October 26th, 2017

* Initial release
