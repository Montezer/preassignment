## Software Management

Ubuntu uses **APT** (Advanced Package Tool) to install, update and remove software packages.

APT downloads packages from configured software repositories and automatically handles package dependencies.

### Common APT Commands

| Command | Description |
|---|---|
| `sudo apt update` | Refresh the list of available packages and versions |
| `sudo apt upgrade` | Upgrade installed packages |
| `sudo apt install <package>` | Install a package |
| `sudo apt remove <package>` | Remove a package but keep its configuration files |
| `sudo apt purge <package>` | Remove a package and its configuration files |
| `apt search <package>` | Search for a package |
| `apt show <package>` | Display information about a package |
| `apt list --installed` | List installed packages |
| `sudo apt autoremove` | Remove dependencies that are no longer needed |

### Example

```bash
sudo apt update
sudo apt install nginx
```

### Why not `yum`

`yum` is **not useless**, but it is irrelevant to my current Ubuntu environment. It is associated with distributions such as older versions of RHEL, CentOS and Amazon Linux.

On modern Red Hat Enterprise Linux, `dnf` is now the main package-management tool, although Red Hat still supports the name `yum` for compatibility. :contentReference[oaicite:1]{index=1}

A simple way to remember it:

| Linux family | Package manager |
|---|---|
| Ubuntu/Debian | `apt` |
| Modern RHEL/Fedora | `dnf` |
| Older RHEL/CentOS | `yum` |

For my current Linux revision, focus on **`apt`**, but recognise `yum` and `dnf` because you may encounter Red Hat or Amazon Linux servers later in DevOps.