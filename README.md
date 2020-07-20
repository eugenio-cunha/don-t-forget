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
    "dns": ["10.0.0.2", "8.8.8.8"]
}
sudo systemctl restart docker

ip addr show

sudo firewall-cmd --get-zone-of-interface= _interface_name_here_

sudo firewall-cmd --zone=FedoraWorkstation --add-masquerade --permanent
sudo firewall-cmd --reload
sudo systemctl restart docker

//test
docker run busybox nslookup google.com
```

## Fix cgroup Fedora Docker

```sh
sudo dnf install grubby
sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"
```
