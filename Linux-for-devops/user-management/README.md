## User Management

In Linux, there are three main types of users:

1. **Superuser or root user**  
   The most powerful user on the system. The root user has full administrative access.

2. **System user**  
   Accounts created for software, applications and background services.

3. **Normal user**  
   Standard user accounts created for people who use the system.

| Type | Examples | Home Directory | Shell |
|---|---|---|---|
| Superuser | `root` | `/root` | `/bin/bash` |
| System user | `ftp`, `sshd`, `apache` | Varies, such as `/var/ftp` | Often `/sbin/nologin` |
| Normal user | `visitor`, `ec2-user` | `/home/<username>` | Usually `/bin/bash` |