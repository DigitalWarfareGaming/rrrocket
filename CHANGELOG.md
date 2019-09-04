## v0.4.2 - September 4th 2019

* Update replay parser to latest version:
  * Support for patch v1.66 games
  * Include attribute object id on actor update, so now one can more easily derive the attribute's name with `replay.objects[attribute.object_id]`

## v0.4.1 - August 13th 2019

* Update replay parser to latest version:
  * Support for haunted and rugby games.
  * Improvement to error handling that gives detailed error messages on what new / updated actor may have received changes in the RL update. These error messages should only be helpful debugging new updates.
  * Several security fixes:
    * Malicious user could craft NumFrames property to be obscenely high and run the machine out of memory. An error is now thrown if the requested number of frames is greater than the number of bytes remaining.
    * A class's network cache that referenced an out of range object id would cause a index out of bound panic. Now an error is raised.
    * Other fixes are for panics in debug builds

## v0.4.0 - June 11th 2019

* 4x performance improvement when printing json to stdout
* Accept replays piped via stdin

## v0.3.0 - June 10th 2019

* Add `-p/--pretty` flag for pretty printing the JSON output

## v0.2.13 - June 5th 2019

* Update replay parser to be compatible with v1.63

## v0.2.12 - June 2nd 2019

* CRC content changed from signed 32bits to unsigned
* Expose additional information about remote ids on reservations

## v0.2.11 - May 24th 2019

* Update replay parser to be compatible with more replays

## v0.2.10 - April 25th 2019

* Serialize 64bit numbers as strings, so that JSON parsers don't lose any data
  in parsing them as 64bit floating point
  * Javascript numbers are 64bit floating point. 64bit integers can't be
    represented wholly in floating point notation. Thus serialize them as
    strings so that downstream applications can decide on how best to interpret
    large numbers (like 76561198122624102). Affects Int64, QWord, Steam, and
    XBox attributes.
* QWord header property changes from i64 to u64 as some pointed out that
  negative numbers didn't make sense for QWord properties (OnlineId)

## v0.2.9 - April 22nd 2019

* Update replay parser to be compatible with v1.61

## v0.2.8 - April 5th, 2019

* Release for rrrocket's new home (split from the boxcars repo). No changes.

## v0.2.7 - April 4th, 2019

* Update replay parser to be compatible with v1.59

## v0.2.6 - September 6th, 2018

* Update replay parser to be compatible with v1.50

## v0.2.5 - May 30th, 2018

* Update replay parser to be compatible with v1.45

## v0.2.4 - April 25th, 2018

* Update replay parser to support current replays

## v0.2.3 - March 18th, 2018

* Add a `--dry-run` option that won't output JSON
* Update replay parser to support current replays

## v0.2.2 - February 14th, 2018

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
