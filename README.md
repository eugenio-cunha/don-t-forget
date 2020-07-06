# Don´t forget!

Não esqueça


## Adicionar usuário ao `sudoers`

```sh
sudo usermod -aG wheel username

sudo visudo

remova o #
...
%wheel ALL=(ALL) ALL
...

```

## Fix DNS Docker

```sh
sudo vim /etc/docker/daemon.json

{
    "dns": ["8.8.8.8", "8.8.4.4"]
}
