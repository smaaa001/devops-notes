# devops-notes

> Personal DevOps learning notes covering Linux, networking, SSH, backend deployment practices and others as needed.

Basic ssh terminal command to generate key-pairs, managing agent, configure hosts, authorized public keys etc.

---

### Note: `<value>` represents a variable to be replaced with actual value




<details>
    <summary><b>Linux OS</b></summary>

## Create a .ssh directory (Optional)

---


```bash
ls -ld ~/.ssh                       # Check if directory exists

mkdir -p ~/.ssh                     # Create .ssh directory

chmod 700 ~/.ssh                    # restrict access to current user only
```



## Generate an SSH key pair

---


```bash
ssh-keygen -t <key-type> -f <filename>      # generate an ssh key
                                            # Ex: ssh-keygen -t ed25519 -f ~/.ssh/rasp_pi_key


ssh-keygen -c -f <private-key-filename>     # add a meaningful comment to public key 
                                            # easy to identify in authorized_keys file
                                            # Ex: ssh-keygen -c -f ~/.ssh/rasp_pi_key

```


## Copy public key to the remote server (automated)

---


```bash
ssh-copy-id -i <public-key-filename> <username>@<remote-server>     # Copy public key to remote server
                                                                    # Ex: ssh-copy-id -i ~/.ssh/rasp_pi_key.pub syed@192.168.4.1
```




## SSH Login using ~/.ssh/config

---

```bash
vim ~/.ssh/config   # open config file
```
```text

Host <nickname>
    HostName <ip-address or server domain>
    User <username>
    IdentityFile <private-key-filename with full path>
    IdentitiesOnly yes
```


Example:
```text
Host pi
    HostName 192.168.4.1
    User syed
    IdentityFile ~/.ssh/pi_lab_key
    IdentitiesOnly yes

```

Login:

```bash
ssh <nickname>    # login using nickname
                  # Ex: ssh pi
```



</details>







<details>
    <summary><b>Mac OS</b></summary>

## Create a .ssh directory (Optional)

---


```bash
ls -ld ~/.ssh                       # Check if directory exists

mkdir -p ~/.ssh                     # Create .ssh directory

chmod 700 ~/.ssh                    # restrict access to current user only
```



## Generate an SSH key pair

---


```bash
ssh-keygen -t <key-type> -f <filename>      # generate an ssh key
                                            # Ex: ssh-keygen -t ed25519 -f ~/.ssh/rasp_pi_key


ssh-keygen -c -f <private-key-filename>     # add a meaningful comment to public key 
                                            # easy to identify in authorized_keys file
                                            # Ex: ssh-keygen -c -f ~/.ssh/rasp_pi_key

```


## Copy public key to the remote server (automated)

---


```bash
ssh-copy-id -i <public-key-filename> <username>@<remote-server>     # Copy public key to remote server
                                                                    # Ex: ssh-copy-id -i ~/.ssh/rasp_pi_key.pub syed@192.168.4.1
```




## SSH Login using ~/.ssh/config

---

```bash
vim ~/.ssh/config   # open config file
```
```text

Host <nickname>
    HostName <ip-address or server domain>
    User <username>
    IdentityFile <private-key-filename with full path>
    IdentitiesOnly yes
```


Example:
```text
Host pi
    HostName 192.168.4.1
    User syed
    IdentityFile ~/.ssh/pi_lab_key
    IdentitiesOnly yes

```

Login:

```bash
ssh <nickname>    # login using nickname
                  # Ex: ssh pi
```



</details>






<details>
    <summary><b>Windows OS (Use Git Bash)</b></summary>

## Create a .ssh directory (Optional)

---


```bash
ls -ld ~/.ssh                       # Check if directory exists

mkdir -p ~/.ssh                     # Create .ssh directory

chmod 700 ~/.ssh                    # restrict access to current user only
```



## Generate an SSH key pair

---


```bash
ssh-keygen -t <key-type> -f <filename>      # generate an ssh key
                                            # Ex: ssh-keygen -t ed25519 -f ~/.ssh/rasp_pi_key


ssh-keygen -c -f <private-key-filename>     # add a meaningful comment to public key 
                                            # easy to identify in authorized_keys file
                                            # Ex: ssh-keygen -c -f ~/.ssh/rasp_pi_key

```


## Copy public key to the remote server (automated)

---


```bash
ssh-copy-id -i <public-key-filename> <username>@<remote-server>     # Copy public key to remote server
                                                                    # Ex: ssh-copy-id -i ~/.ssh/rasp_pi_key.pub syed@192.168.4.1
```




## SSH Login using ~/.ssh/config

---

```bash
vim ~/.ssh/config   # open config file
```
```text

Host <nickname>
    HostName <ip-address or server domain>
    User <username>
    IdentityFile <private-key-filename with full path>
    IdentitiesOnly yes
```


Example:
```text
Host pi
    HostName 192.168.4.1
    User syed
    IdentityFile ~/.ssh/pi_lab_key
    IdentitiesOnly yes

```

Login:

```bash
ssh <nickname>    # login using nickname
                  # Ex: ssh pi
```



</details>
