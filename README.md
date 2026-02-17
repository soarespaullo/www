## 🔄 Backup Automatizado do Sistema (MySQL + /var/www)

Este script realiza o **backup automático da pasta `/var/www` e de todos os bancos de dados MySQL** de forma segura, com compressão, verificação de espaço em disco e interface amigável via terminal.

---

## 📦 Funcionalidades

- Backup da pasta `/var/www` com compactação `.tar.gz`
- Backup individual de todos os bancos de dados MySQL
- Barra de progresso com [`pv`](https://linux.die.net/man/1/pv)
- Verificação de espaço em disco antes de cada backup
- Interface interativa com validações e feedback em cores
- Criação automática do diretório de destino, se necessário

---

## ⚙️ Requisitos

- Executar como **root** (`sudo`)
- Dependências instaladas:
  - `mysqldump`
  - `tar`
  - `gzip`
  - `pv`
- MySQL acessível localmente
- Recomendado: Arquivo de configuração `~/.my.cnf` com as credenciais para evitar prompts de senha

Exemplo de `.my.cnf` (proteja com `chmod 600 ~/.my.cnf`):

```
[client]
user=root
password=SUASENHA
```

---

## 🚀 Como Usar

1. **Clone o repositório:**

```
git clone https://github.com/soarespaullo/www.git
```

2. **Dê permissão de execução ao script:**

```
chmod +x www.sh
```

3. **Execute o script como root:**

```
sudo ./www.sh
```

**Informe o diretório de destino do backup quando solicitado:**

```
Caminho do destino do backup (ex: /media/backup): /mnt/hdexterno
```

---

## 📁 Estrutura dos Arquivos de Backup

- `/mnt/hdexterno/var_www_backup_11-05-2025_15-30-00.tar.gz`

- `/mnt/hdexterno/meubanco_backup_11-05-2025_15-30-00.sql.gz`

---

## 🛑 Observações Importantes

Evite usar `:` nos nomes de arquivos — o script já faz isso automaticamente substituindo por `-`.

Certifique-se de que o dispositivo de destino (HD externo, partição, etc.) está montado e possui espaço suficiente.

O script ignora os bancos padrão do MySQL (`information_schema`, `performance_schema`, etc.).

---

## 🧪 Testado em:

Ubuntu Server 20.04 / 22.04

Debian 11+

MySQL 5.7 / 8.0

---

## 📄 Licença

Este projeto é licenciado sob a licença MIT. Veja o arquivo [LICENSE](https://github.com/soarespaullo/www/blob/main/LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

**Paulo Soares**

- 📧 [**soarespaullo@proton.me**](mailto:soarespaullo@proton.me)

- 💬 [**@soarespaullo**](https://t.me/soarespaullo) no Telegram

- 💻 [**GitHub**](https://github.com/soarespaullo)

- 🐞 [**NotABug**](https://notabug.org/soarespaullo)
