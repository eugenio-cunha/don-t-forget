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

## SDK Android

```sh
/home/&{USER}/Android/Sdk/cmdline-tools/tools
```

## Restore Mongodb 
```sh
docker run --rm -v ~/Documents/dump:/dump mongo mongorestore --host 172.17.0.2:27017 /dump

# Exemplo
docker run --rm -v /home/user_name/Document/dump:/dump mongo mongorestore --host _ip_container:27017 --gzip --archive=dump/database_name.zip
```

## Pesquisar arquivos acima de N MB
```sh
sudo find / -type f -size +10M -exec ls -lh {} \;
```

## Logs do sistema
```sh
du -h /var/log/journal
journalctl --disk-usage
sudo journalctl --vacuum-size=300M
```



