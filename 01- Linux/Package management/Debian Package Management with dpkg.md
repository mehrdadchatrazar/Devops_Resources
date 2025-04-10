# Debian Package Management with dpkg

This document outlines common `dpkg` commands used for Debian package management, along with explanations and examples.

## Basic Package Installation and Removal

* **`-i, --install <package.deb>`:** Install a `.deb` package.

    ```bash
    sudo dpkg -i mypackage.deb
    ```

    This command installs the specified package. If dependencies are missing, `dpkg` will report an error.

* **`-r, --remove <package_name>`:** Remove a package, but leave its configuration files.

    ```bash
    sudo dpkg -r mypackage
    ```

    This uninstalls the package, but configuration files in `/etc` and other locations are preserved.

* **`-P, --purge <package_name>`:** Remove a package and its configuration files.

    ```bash
    sudo dpkg -P mypackage
    ```

    This completely removes the package and its associated configuration files.

## Package Information

* **`-s, --status <package_name>`:** Display package status information.

    ```bash
    dpkg -s mypackage
    ```

    This command shows detailed information about the installed package, including its version, architecture, and dependencies.

* **`-L, --listfiles <package_name>`:** List files installed by a package.

    ```bash
    dpkg -L mypackage
    ```

    This command displays the list of files that were installed by the specified package.

* **`-S, --search <filename>`:** Search for a package that owns a file.

    ```bash
    dpkg -S /usr/bin/somecommand
    ```

    This command searches for the package that installed the specified file. This is useful for determining which package provides a particular executable or library.

* **`-l [<package_name_pattern>]`:** List installed packages.

    ```bash
    dpkg -l
    dpkg -l '*apache*' # List packages with 'apache' in their name
    ```

    This command lists all installed packages. You can use wildcard patterns to filter the results.

## Important Notes

* `dpkg` primarily deals with the installation and removal of `.deb` files. It does *not* handle dependency resolution. For resolving dependencies, use `apt` or `apt-get`.
* Always use `sudo` when running `dpkg` commands that modify the system.
* Carefully review any error messages from `dpkg` to avoid potential system issues.