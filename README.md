## Repositorio Ansible

Este repositorio tem finalidade a finalidade de aprendizado e maior familiaridade com a ferramenta.

# - Utilização 

É de extrema importancia que o os host que serão gerenciados pelo ansible tenham a troca de chaves ssh efetuado entre o manager.
Para isso gera as chaves ssh em cada um dos nós gerenciados via ansible.

Rode o comando no ansible manager:
-  `ssh-keygen -t rsa -b 4096 -C "ansible-manager" -f ~/.ssh/NOME_DA_CHAVE" `

Rode o comando nos nós gerenciados:
- `ssh-keygin -t rsa -b 4096`

O Comando acima irá gera um par de chaves publica e privada dentro da pasta `~/.ssh/`

OBS.: Podemos alterar o valor <strong>ansible-manger</strong> e <strong>NOME_DA_CHAVE</strong> para o valor que desejarmos.

# Habilitando ao ssh via chave privada

Apos efetuar o par de chaves nos nós gerenciados via ansible roda os comandos abaixo em cada nó para compartilhar a chave gerada:

## Nós gerenciados
 
    - `ssh-copy-id -i ~/.ssh/NOME_DA_CHAVE usuario@ip_ansible_manager`
    - `ssh-copy-id -i ~/.ssh/NOME_DA_CHAVE usuario@ip_ansible_manager`
    - `ssh-copy-id -i ~/.ssh/NOME_DA_CHAVE usuario@ip_ansible_manager`

## Ansible manager

- `ssh-copy-id -i ~/.ssh/NOME_DA_CHAVE usuario@ip_ansible_manager`

    Fazer para 

# Comandos Ansible



1 - Executar um teste de conexão

