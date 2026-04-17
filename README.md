# Cap 1 - Setup Híbrido (VM + EC2) & SSH

Prepara o ambiente que vai hospedar o Giropops Status: VM local no VirtualBox + EC2 t2.micro na AWS, conectados via SSH com `~/.ssh/config`.

## Entregas

- VM local Ubuntu acessível via SSH com alias no `~/.ssh/config`
- EC2 t2.micro provisionada e acessível via SSH
- `ssh-copy-id` funcionando nos dois ambientes
- `apt update` rodando em paralelo nos dois terminais

---

## Ações Realizadas

- VM será criada localmente com o Vagrant usando o VirtualBox
- Criar módulo Terraform para criar estrutura de VM na AWS
