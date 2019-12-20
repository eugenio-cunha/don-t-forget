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
