# MySQL 8.0 – Instalação e Configuração Inicial (RHEL 8)

## Visão Geral

Este repositório contém a documentação oficial para **instalação, configuração inicial e hardening básico do MySQL Community Server 8.0** em sistemas baseados em **RHEL 8** (Oracle Linux, Rocky Linux, AlmaLinux).

O objetivo é padronizar o processo de instalação, facilitar auditorias, onboarding de novos profissionais e garantir reprodutibilidade em ambientes de **laboratório, homologação e produção**.

---

## Escopo

✔ Instalação do MySQL 8.0 via repositório oficial  
✔ Configuração de repositórios com `dnf`  
✔ Inicialização e validação do serviço  
✔ Recuperação da senha temporária do usuário `root`  
✔ Hardening inicial (`mysql_secure_installation`)  
✔ Strings de conexão (CLI e aplicações)  
✔ Configuração de firewall  

❌ Este repositório **não cobre**:
- Tuning avançado de performance
- Replicação, Group Replication ou InnoDB Cluster
- Backup avançado (XtraBackup, MySQL Enterprise Backup)
- Monitoramento

---

## Sistemas Operacionais Suportados

- Oracle Linux 8
- Red Hat Enterprise Linux 8
- Rocky Linux 8
- AlmaLinux 8

---

## Pré-requisitos

- Acesso `root` ou usuário com privilégios `sudo`
- Conectividade com a internet
- DNS e horário do sistema corretamente configurados
- Firewall ativo (`firewalld`)

---

## Estrutura do Repositório

```text
.
├── README.md
└── MYSQL_INSTALL_RHEL8.md
