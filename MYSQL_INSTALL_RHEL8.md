# MySQL 8.0 – Instalação e Configuração Inicial (RHEL 8)

## Visão Geral

Este documento padroniza o processo de **instalação, configuração inicial e hardening básico do MySQL Community Server 8.0** em sistemas baseados em **RHEL 8** (Oracle Linux, Rocky Linux, AlmaLinux).

Destina-se a ambientes corporativos para:
- Laboratório
- Homologação
- Produção (nível básico)
- Onboarding técnico
- Auditoria e handover

---

## Escopo

✔ Instalação do MySQL 8.0 via repositório oficial  
✔ Uso do `dnf`  
✔ Inicialização e validação do serviço  
✔ Recuperação da senha temporária do `root`  
✔ Hardening inicial  
✔ Strings de conexão  
✔ Configuração de firewall  

---

## Sistemas Operacionais Suportados

- Oracle Linux 8
- Red Hat Enterprise Linux 8
- Rocky Linux 8
- AlmaLinux 8

---

## Pré-requisitos

- Acesso `root` ou `sudo`
- Internet
- Firewall ativo (`firewalld`)
- Data e hora corretas

---

## 1. Download do repositório MySQL

```bash
wget https://dev.mysql.com/get/mysql84-community-release-el8-2.noarch.rpm
```

---

## 2. Instalação do repositório

```bash
sudo dnf install -y mysql84-community-release-el8-2.noarch.rpm
```

---

## 3. Configuração da versão do MySQL

```bash
sudo dnf install -y dnf-utils
sudo dnf config-manager --disable mysql-8.4-lts-community
sudo dnf config-manager --enable mysql80-community
```

---

## 4. Instalação do MySQL Server

```bash
sudo dnf install -y mysql-community-server
```

---

## 5. Inicialização do serviço

```bash
systemctl status mysqld
sudo systemctl start mysqld
sudo systemctl enable mysqld
```

---

## 6. Recuperar senha temporária do root

```bash
sudo grep 'temporary password' /var/log/mysqld.log
```

---

## 7. Hardening inicial

```bash
mysql_secure_installation
```

---

## 8. Strings de conexão

```text
mysql://usuario:senha@host:porta/banco
```

---

## 9. Firewall

```bash
sudo firewall-cmd --permanent --add-port=3306/tcp
sudo firewall-cmd --reload
```

---

## Conclusão

MySQL 8.0 instalado e pronto para uso.
