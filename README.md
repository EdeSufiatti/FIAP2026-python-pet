# 🐾 CRUD Petshop com Python + Oracle

Projeto desenvolvido em Python para gerenciamento de pets utilizando banco de dados Oracle.

Este sistema implementa operações CRUD (Create, Read, Update, Delete) via terminal.

---

## 🚀 Funcionalidades

- Cadastrar pet
- Listar pets
- Alterar pet
- Excluir pet
- Excluir todos os registros
- Conexão com Oracle Database

---

## 🛠️ Tecnologias utilizadas

- Python 3.12
- Oracle Database XE
- Oracle SQL Developer
- oracledb
- pandas
- python-dotenv

---

## 📁 Estrutura do projeto

pet/
├── main.py
├── .env
├── .gitignore
└── README.md

---

## ⚙️ Pré-requisitos

Antes de rodar o projeto, você precisa ter instalado:

- Python 3.12+
- Oracle Database XE (Windows)
- Oracle SQL Developer

---

# 🧱 Instalação do Oracle Database XE (Windows)

### 1. Download

Baixe o Oracle Database XE (Express Edition) no site oficial da Oracle:

https://www.oracle.com/database/technologies/xe-downloads.html

---

### 2. Instalação

Execute o instalador e siga os passos:

- Defina uma senha para os usuários administrativos (SYSTEM/SYS)
- Mantenha a porta padrão: **1521**
- Aguarde a instalação concluir

---

### 3. Verificar instalação

Após instalar, o Oracle já cria automaticamente:

- Banco local ativo
- Serviço padrão: **XEPDB1**

Esse será o banco utilizado no projeto.

---

# 🔌 Configuração do SQL Developer

1. Abra o SQL Developer
2. Crie uma nova conexão com os seguintes dados:

- Host: `127.0.0.1`
- Porta: `1521`
- Service name: `XEPDB1`
- Usuário: `system`
- Senha: (definida na instalação)

3. Clique em **Testar** → **Conectar**

---

# 👤 Criar usuário no Oracle XE

No SQL Developer, execute os comandos abaixo:

ALTER SESSION SET CONTAINER = XEPDB1;

CREATE USER <seu_user_oracle> IDENTIFIED BY <sua_senha_oracle>;

GRANT CONNECT, RESOURCE TO <seu_user_oracle>;

ALTER USER <seu_user_oracle> QUOTA UNLIMITED ON USERS;

---

# 🗄️ Criar tabela do projeto

Conectado com o usuário criado, execute:

CREATE TABLE petshop(
 id NUMBER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
 tipo_pet VARCHAR2(30),
 nome_pet VARCHAR2(30),
 idade INT
);

---

## 🔐 Configuração do .env

Crie um arquivo `.env` na raiz do projeto (não versionar):

DB_USER=<seu_user_oracle>
DB_PASSWORD=<sua_senha_oracle>
DB_HOST=127.0.0.1
DB_PORT=1521
DB_SERVICE=XEPDB1

---

## 📦 Instalação das dependências

No terminal:

pip install oracledb pandas python-dotenv

---

## ▶️ Como executar o projeto

python main.py

---

## 🖥️ Exemplo de uso

------- CRUD - PETSHOP -------

1 - Cadastrar Pet
2 - Listar Pets
3 - Alterar Pet
4 - Excluir Pet
5 - EXCLUIR TODOS OS PETS
6 - SAIR

---

## ⚠️ Segurança

- Nunca envie o arquivo `.env` para o Git
- Adicione `.env` no `.gitignore`
- Nunca exponha credenciais no código ou README

---

## 📌 Possíveis erros

Erro de conexão:
- Verifique variáveis no `.env`
- Verifique se o Oracle está rodando
- Confirme o uso de `127.0.0.1:1521/XEPDB1`

Tabela não encontrada:
- Execute o script de criação da tabela

Permissão negada:
Execute:

GRANT CONNECT, RESOURCE TO <seu_user_oracle>;
ALTER USER <seu_user_oracle> QUOTA UNLIMITED ON USERS;

---

## 📚 Conceitos aplicados

- CRUD (Create, Read, Update, Delete)
- Conexão com banco Oracle via Python
- Manipulação de dados com Pandas
- Uso de variáveis de ambiente (.env)
- Tratamento de erros com try/except

---

## 👨‍💻 Autor

Projeto desenvolvido para fins acadêmicos.