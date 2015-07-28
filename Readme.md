# Overview

To configure and run luncher follow steps below.

1.  Create configuration file with following content:

    LAUNCHER_BASE: <path-to-the-launcher-menu-dir>
    cmd: <cmd-prefix>

    Where "LAUNCHER_BASE" specifies the path to the directory
    with all launcher menu files and "cmd" specifies the prefix
    which will be added to all commands. e.g.:

    LAUNCHER_BASE: ./menus/
    cmd: bash -c

2.  Prepare menu configurations in comma separated value format
    (see end of this file for details) and save them to the
    directory specified with "LAUNCHER_BASE".

3.  Start the launcher wit following command:
        launcher.py <name-of-menu-file> <path-to-config-file>

    To run the launcher with example configuration run:
        launcher.py F_DI_BAM_BAM3-Main.csv ./config/config.ini

    Run "launcher -h" to access the help.

-----------------------------------------------
-----------------------------------------------

Currently comma separated value configuration format is supported (for details check examples in ./menus/ directory) with additional support for comments.

Following items are currently supported:

- Main menu title which is shown as label of main launcher button. Only one should be defined
        main-title,"This is menu title"

- comment
        # This is some comment.

- separator to visually separate menu items
        separator

- "title" is a special separator with text
    title,"This is text"

- Button which executes shell command defined in parameter. parameter is combined with "cmd" parameter in configuration file (e.g. bash -c 'parameter').
        cmd,"This is button text",parameter

- Button which opens submenu defined in different file.
        menu,"This is button text",submenu-file-name

- Menu item which opens another menu defined in different file (for example to open user/expert view)
        file-choice,"This is button text",menu-file-name