# tobyink's development tools

## bin/pp

Shortcut to run various Perl development tools from the command line. The script is designed so that if your current working directory is somewhere deeply nested in your project directory, the commands will change to the project directory before running. The idea is for this to be a starting point that you can customize each command for your own development environment/style, add your own commands, etc.

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

## bin/my-perltidy

tobyink's perltidy script. It's customized to my preferred indentation rules, etc.
