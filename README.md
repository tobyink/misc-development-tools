# tobyink's development tools

## Command-Line Tools

### bin/pp

Shortcut to run various Perl development tools from the command line. The script is designed so that if your current working directory is somewhere deeply nested in your project directory, the commands will change to the project directory before running. (pp determines the project directory using the existence of a "t" directory within it, which should typically contain the project's test suite, though an empty directory will suffice.)

The idea is for this to be a starting point that you can customize each command for your own development environment/style, add your own commands, etc.

* `pp run FILENAME` - runs a script in Perl, adding `PROJECTDIR/lib` and `PROJECTDIR/inc` to `@INC`
* `pp test` - runs test suite (requires App::Yath)
* `pp xtest` - runs test suite with `$ENV{EXTENDED_TESTING} = 1` (requires App::Yath)
* `pp tidyall` - processes project files using my-perltidy
* `pp ws` - checks project files using Test::Tabs
* `pp gh` - open the project's GitHub page in browser (requires xdg-open)
* `pp travis` - open the project's Travis-CI.com page in browser (requires xdg-open)
* `pp coveralls` - open the project's Coveralls.io page in browser (requires xdg-open)
* `pp check` - builds distribution using Dist::Inkt and opens a shell in the built distribution
* `pp release` - builds distribution using Dist::Inkt and releases to CPAN
* `pp ppedit` - opens pp itself in GNU Nano
* `pp help` - list known commands

Running `pp` by itself runs `pp test`.

### bin/my-perltidy

tobyink's perltidy script. It's customized to my preferred indentation rules, etc.

## Atom config

Config files for the atom.io editor. These rely on the command-line tools above, plus the x-terminal, flex-tool-bar, and terminal-commands plugins. They also assume you'll mostly be working on projects that use either Make or Dist::Inkt for build/deployment, and use Mercurial for version control. If you use other tools, it shouldn't be rocket science to tweak these config files.

[web-typetiny](https://github.com/tobyink/web-typetiny) includes an example Makefile and toolbar.cson to add project-specific buttons to the Atom toolbar.
