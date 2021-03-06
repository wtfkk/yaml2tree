⛔️ &nbsp;&nbsp;DEPRECATED  

[mktree](https://github.com/prfxn/recipes/blob/main/shell/mktree.zsh) and [rrmdir](https://github.com/prfxn/recipes/blob/main/shell/rrmdir.zsh) offer a better / simpler solution.

[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

# yaml2tree
Creates a tree of directories, specified using nested lists in YAML

### Usage: 

    [mode=XXX] yaml2tree <yaml-file>

        mode=XXX       set this env var to provide a chmod-style octal value to use as file mode
                       for the created directories.

        <yaml-file>    path to YAML file containing the directory tree specification.
                       The YAML is a list of values, where every value is either a directory name
                       or a list of the same form. The YAML is processed top-down and whenever a
                       nested list is encountered, any directories in it are created inside the 
                       directory last seen on the outer list.
    
                       For example, the following definition -
                           - foo
                           -   - bar
                               - baz
                               - tam
                           - foo1
                           -   - bar2
                               -   - baz3
                           - soap
    
                       creates the following directory tree in the current working directory -
                           foo/
                               bar/
                               baz/
                               tam/
                           foo1/
                               bar2/
                                   baz3/
                           soap/
