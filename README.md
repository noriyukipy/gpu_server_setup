# GPU Server setup - Ubuntu Server 18.04.3 LTS

## Requrements

- Install [Ubuntu Server 18.0.4.3 LTS](https://ubuntu.com/download/server) to your server.
- RTX 2080 Ti is required
- Install Ansible to the server
  ```sh
  $ sudo apt install ansible
  ```

## Copy public key

```sh
ssh-copy-id -i /path/to/your_public_key 192.168.0.3
```

## Check connection

```sh
$ ansible -i inventory.ini all -m ping
192.168.0.3 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

## Run Ansible

```Sh
$ ansible-playbook -i inventory.ini main.yml --become --ask-become-pass
```