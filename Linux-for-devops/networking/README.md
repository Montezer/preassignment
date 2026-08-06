## Networking

| Command | Description |
|---|---|
| `hostname` | Display the hostname of the system |
| `hostname -I` | Display the system's IP address |
| `ping <hostname-or-ip>` | Test whether another host is reachable over the network |
| `wget <URL>` | Download a file from a URL |
| `ip address` | Display network interfaces and IP addresses |
| `ip route` | Display the system's routing table |
| `curl <URL>` | Send a request to a URL and display the response |
| `curl -I <URL>` | Display only the HTTP response headers |
| `ss -tulpn` | Display listening network ports and the processes using them |
| `nc -zv <host> <port>` | Test whether a specific port is reachable |

`ifconfig → ip address`: 
- ifconfig is considered outdated and may not be installed by default on Ubuntu.

`telnet → nc -zv`: 
- Telnet is insecure for remote access and is generally replaced by SSH. For checking whether a port is open, nc—Netcat—is more suitable.

----------

## Using `nc -zv`

`nc` stands for **Netcat**. It is a networking tool that can be used to test whether a specific port on another machine is reachable.

### Syntax

```bash
nc -zv <host> <port>
```

### Options

| Option | Meaning |
|---|---|
| `-z` | Scan the port without sending any data |
| `-v` | Use verbose mode and display more information |

### Basic Example

```bash
nc -zv 192.168.1.20 22
```

This checks whether port `22` is reachable on the server with the IP address `192.168.1.20`.

Port `22` is normally used by SSH.

### Successful Result

```text
Connection to 192.168.1.20 22 port [tcp/ssh] succeeded!
```

This means:

- The server is reachable
- The port is open
- A service is listening on that port

### Connection Refused

```text
nc: connect to 192.168.1.20 port 22 (tcp) failed: Connection refused
```

This normally means:

- The server is reachable
- The port is closed
- Nothing is listening on that port

### Connection Timed Out

```text
nc: connect to 192.168.1.20 port 22 (tcp) timed out
```

This could mean:

- The server is unreachable
- A firewall is blocking the connection
- A cloud security group does not allow the port
- The IP address is incorrect

## Testing Common Ports

### Test SSH

```bash
nc -zv 192.168.1.20 22
```

### Test HTTP

```bash
nc -zv 192.168.1.20 80
```

### Test HTTPS

```bash
nc -zv 192.168.1.20 443
```

### Test MongoDB

```bash
nc -zv 192.168.1.20 27017
```

### Test an Application Running on Port 3000

```bash
nc -zv 192.168.1.20 3000
```

## Testing a Hostname

A hostname or domain name can be used instead of an IP address:

```bash
nc -zv example.com 443
```

This checks whether HTTPS port `443` is reachable on `example.com`.

## Testing Multiple Ports

Multiple ports can be checked at the same time:

```bash
nc -zv 192.168.1.20 22 80 443
```

This checks ports `22`, `80` and `443` on the same server.

## Testing a Range of Ports

A range of ports can also be checked:

```bash
nc -zv 192.168.1.20 20-25
```

This checks every port from `20` to `25`.

## DevOps Example

Imagine an application server needs to connect to a MongoDB server.

You can test the connection using:

```bash
nc -zv 10.0.3.127 27017
```

If the connection succeeds, the application server can reach the MongoDB port.

If the connection fails, check:

- Whether MongoDB is running
- Whether MongoDB is listening on port `27017`
- Whether the firewall allows the connection
- Whether the cloud security group allows the connection
- Whether the correct private IP address is being used
- Whether both machines are connected to the correct network

> **Note:** `nc -zv` only checks whether a port is reachable. It does not confirm that the application or service behind the port is working correctly.