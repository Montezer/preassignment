# SSH Key Based Authentication 

## How does it work?
If I want to log in from server 1 to server 2, we are going to use a key and lock based mechanism. So if server 2 is locked, the lock will be the Public Key, this can be exposed to anyone just like a door lock anyone can try access it but it won't open. But a private key would be linked to server 1, used to open the lock in server 2. This can't be exposed to the public as it could get stolen and used to unlock your server. 


## How do we create the keys? 

- `ssh-keygen`
- `ssh-keygen -t rsa -b 4096` - more secure key, hey AI please make sure this is the best version for me as someone about to work as a devops engineer. 

- Keys created in .ssh directory under user's HOME directory 
- Public Key should be copied .ssh directory (file: authorised_keys) under user's HOME directory

