# to

A simple script for bookmarking directory locations with tab completion.

This fork only exists to support macOS 10.14+.

## Installation

Shells currently supported are bash and zsh.  Other shells may be compatible, but they have not been tested.

### Install dependencies - GNU tools

Install via [Homebrew](https://brew.sh/):

```
$ brew install coreutils findutils
```

### Add to `.profile`

Source this script in your shell's initialization file, e.g. `.profile`:

```bash
source ~/path/to/to.sh
```


## Usage

to [OPTION] [BOOKMARK] [DEST]

Options

* __-b__ : Add a new bookmark for current directory (overwrites any current bookmark)
* __-r__ : Remove bookmark
* __-p__ : Print bookmark path
* __-h__ : Show help

Other than -h, only the first option given is ever used.

### Examples

print all bookmarks
> to

go to the foo bookmark (if exists)
> to foo

go to the directory bar inside the directory foo points to (if exists)
> to foo/bar

create a bookmark with the name of the current directory pointing to it
> to -b

set the foo bookmark to the current directory
> to -b foo

set the foo bookmark to the /bar/baz directory
> to -b foo /bar/baz

remove the foo bookmark
> to -r foo

print the path of the foo bookmark
> to -p foo

open up bar.cpp at the foo bookmark in vim
> vim $(to -p foo/bar.cpp)

You can also manually edit the $TO_BOOKMARK_DIR folder (defined in `to.sh`, default `~/.bookmarks`)
which contains symbolic links that represent your bookmarks. You can switch to this directory with:
> to .


## Dependencies

* bash or zsh

The following functionality should either be provided or built in:

* cd
* ln
* readlink
* mkdir
* rm
* read
* printf
* find
* dirname
* basename

## License

to - v1.4.5

Copyright (C) 2013  Mara Kim, Philipp Adolf, Max Thrun, Rob Adams

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
