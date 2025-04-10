# Debian Package Management with APT

**Note:** Most APT commands require superuser privileges. Prefix them with `sudo` (e.g., `sudo apt update`) if you are not running as the root user.

## Configuring Repositories

APT relies on repository servers that host software packages to download and install software. Repository configurations are stored in the `/etc/apt/sources.list` file and the `/etc/apt/sources.list.d/` directory. Below, I outline how to set mirrors and repositories for both Debian and Ubuntu.

### For Debian

In Debian, the primary repository configuration file is `/etc/apt/sources.list`. You can edit this file to add or modify repository mirrors. For example, to include the `main`, `contrib`, and `non-free` repositories for a Debian release (e.g., Bookworm), add or uncomment lines like this:

```bash
deb http://deb.debian.org/debian/ bookworm main contrib non-free
deb-src http://deb.debian.org/debian/ bookworm main contrib non-free
```

- Replace `bookworm` with your Debian release codename (e.g., `bullseye`, `bookworm`).
- `deb` lines specify binary packages; `deb-src` lines allow downloading source code.
- After editing, run `sudo apt update` to refresh the package index.

### For Ubuntu

In Ubuntu, While modern Ubuntu versions may use `.sources` files in `/etc/apt/sources.list.d/` for specific configurations, the traditional file is still `/etc/apt/sources.list`. You can edit either to set mirrors. For example:

```bash
deb http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse
```

- Replace `jammy` with your Ubuntu release codename (e.g., `focal`, `jammy`).
- Alternatively, add files to `/etc/apt/sources.list.d/` (e.g., `ubuntu.sources`) with similar entries.

## Updating and Upgrading

Before installing or managing packages, it’s important to update your package index to ensure you're getting the latest package information:

- **Update package index:**
```bash
  apt update
```

Upgrade installed packages:

```bash
apt upgrade
```

The `apt update` command retrieves the latest package lists, and `apt upgrade` updates installed packages to their newest available versions.

## Everyday APT Commands
Here are several useful commands that you can use daily when managing your Debian-based system.

### Installing Packages
To install a new package, simply use:
```bash
apt install package_name
```
Replace `package_name` with the name of the package you wish to install.

### Removing and Purging Packages
There are two main options for package removal:

#### Remove a package (keeps configuration files):

```bash
apt remove package_name
```

#### Purge a package (removes configuration files as well):

```bash
apt purge package_name
```

### Searching and Listing Packages
Finding packages and reviewing what is available is often necessary:

#### Search for a package by keyword:

```bash
apt search keyword
```

#### Show detailed information about a package:

```bash
apt show package_name
```

#### List installed packages or available packages (for filtering and review):

```bash
apt list --installed
```


### Cleaning Up
Over time, the package cache and unused dependencies can accumulate:


#### Remove orphaned dependencies:

```bash
apt autoremove
```
- Removes packages that were automatically installed as dependencies but are no longer needed.
- Example: `sudo apt autoremove` cleans up after uninstalling a package.

#### Clean up the local repository of retrieved package files:

```bash
apt clean
```

- Deletes all downloaded package files from the local cache (`/var/cache/apt/archives/`), freeing up disk space.
- Run `sudo apt clean` to clear the cache completely.

These commands help keep your system lean and free up disk space.

### Distribution Upgrades
For handling more complex system upgrades that may introduce new dependencies or require removing packages, use:

```bash
apt dist-upgrade
```