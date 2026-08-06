## Managing Services

Modern Linux systems such as Ubuntu use **`systemctl`** to manage services.

A service is a background process that performs a particular task, such as:

- Running an Nginx web server
- Running an SSH server
- Running a database
- Running Docker

### Common `systemctl` Commands

| Command | Description |
|---|---|
| `sudo systemctl status <service>` | Check the current status of a service |
| `sudo systemctl start <service>` | Start a service |
| `sudo systemctl stop <service>` | Stop a service |
| `sudo systemctl restart <service>` | Stop and start a service again |
| `sudo systemctl reload <service>` | Reload the service configuration without fully restarting it |
| `sudo systemctl enable <service>` | Configure a service to start automatically when the system boots |
| `sudo systemctl disable <service>` | Prevent a service from starting automatically when the system boots |
| `systemctl is-active <service>` | Check whether a service is currently running |
| `systemctl is-enabled <service>` | Check whether a service is configured to start on boot |
| `systemctl list-units --type=service` | List currently loaded services |
| `systemctl list-units --type=service --state=running` | List services that are currently running |

## Example: Managing Nginx

### Check the Status

```bash
sudo systemctl status nginx
```

This shows whether Nginx is running, stopped or experiencing an error.

### Start Nginx

```bash
sudo systemctl start nginx
```

This starts Nginx immediately.

### Stop Nginx

```bash
sudo systemctl stop nginx
```

This stops the Nginx service.

### Restart Nginx

```bash
sudo systemctl restart nginx
```

This stops and starts Nginx again.

A restart is commonly used after changing a configuration file.

### Reload Nginx

```bash
sudo systemctl reload nginx
```

This reloads the Nginx configuration without completely stopping the service.

### Start Nginx Automatically on Boot

```bash
sudo systemctl enable nginx
```

This configures Nginx to start whenever the machine boots.

### Disable Automatic Startup

```bash
sudo systemctl disable nginx
```

This prevents Nginx from starting automatically when the machine boots.

> **Important:** `start` and `enable` do different things.  
> `start` runs the service now, while `enable` configures it to run automatically after boot.

## Start and Enable a Service Together

You can start a service now and enable it for future boots using:

```bash
sudo systemctl enable --now nginx
```

## Viewing Service Logs

Services managed by `systemd` usually store their logs in the system journal.

```bash
sudo journalctl -u nginx
```

This displays logs for the Nginx service.

To view the most recent logs:

```bash
sudo journalctl -u nginx -n 50
```

To follow new logs as they appear:

```bash
sudo journalctl -u nginx -f
```

Press `Ctrl + C` to stop following the logs.

## Why the Commands from the Slide Were Changed

The slide uses:

```bash
service
chkconfig
```

These commands are associated with older Linux service-management systems.

Most modern Linux distributions use **`systemd`**, which is managed using:

```bash
systemctl
```

The old command:

```bash
service nginx start
```

is replaced by:

```bash
sudo systemctl start nginx
```

The old command:

```bash
chkconfig nginx on
```

is replaced by:

```bash
sudo systemctl enable nginx
```

The `service` command may still work on some systems as a compatibility command, but `systemctl` is the modern command you should focus on for Ubuntu and most current Linux servers.

`chkconfig` is mainly associated with older Red Hat-based systems and is normally not used on Ubuntu.