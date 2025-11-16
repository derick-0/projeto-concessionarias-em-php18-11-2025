# projeto-concessionarias-em-php18-11-2025
🚗 Sistema de Concessionária
Descrição

O Sistema de Concessionária é uma aplicação web desenvolvida em PHP e MySQL que permite gerenciar uma concessionária de veículos.
O sistema permite cadastrar funcionários, clientes, modelos de veículos, vendas e gerar relatórios de forma prática e organizada.

Funcionalidades
1. Cadastro de Funcionários

Nome

CPF

E-mail

Telefone

2. Cadastro de Clientes

Nome do Cliente

CPF

E-mail

Telefone

Data de Nascimento

3. Cadastro de Modelos de Veículos

Marca do veículo

Nome do modelo

Cor

Ano

Placa

4. Gerenciamento de Vendas

Seleção de cliente

Seleção de veículo

Data da venda (gerada aleatoriamente ou manualmente)

Valor da venda

5. Tabela de Preços

Consulta e atualização de preços de veículos cadastrados

Tecnologias Utilizadas

Linguagem: PHP

Banco de Dados: MySQL

Servidor Local: XAMPP

Front-end: HTML, CSS e Bootstrap (opcional)

Estrutura do Projeto
/projeto-concessionaria
│
├─ index.php
├─ cadastrar-cliente.php
├─ cadastrar-funcionario.php
├─ cadastrar-modelo.php
├─ listar-vendas.php
├─ salvar-cliente.php
├─ salvar-funcionario.php
├─ salvar-modelo.php
├─ config.php
└─ /assets
   ├─ /css
   └─ /js

Instalação

Clone o repositório:

git clone https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git


Copie os arquivos para a pasta htdocs do XAMPP.

Crie o banco de dados no MySQL:

CREATE DATABASE concessionaria;


Importe as tabelas do arquivo banco.sql (se houver).

Abra o navegador e acesse:

http://localhost/projeto-concessionaria/

Exemplo de Tabelas no Banco de Dados

Tabela funcionarios:

CREATE TABLE funcionarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(100),
  cpf VARCHAR(14),
  email VARCHAR(100),
  telefone VARCHAR(15)
);


Tabela clientes:

CREATE TABLE clientes (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(100),
  cpf VARCHAR(14),
  email VARCHAR(100),
  telefone VARCHAR(15),
  data_nascimento DATE
);


Tabela modelos:

CREATE TABLE modelos (
  id INT AUTO_INCREMENT PRIMARY KEY,
  marca VARCHAR(50),
  nome_modelo VARCHAR(50),
  cor VARCHAR(20),
  ano INT,
  placa VARCHAR(10),
  preco DECIMAL(10,2)
);


Tabela vendas:

CREATE TABLE vendas (
  id INT AUTO_INCREMENT PRIMARY KEY,
  cliente_id INT,
  modelo_id INT,
  data_venda DATE,
  valor DECIMAL(10,2),
  FOREIGN KEY (cliente_id) REFERENCES clientes(id),
  FOREIGN KEY (modelo_id) REFERENCES modelos(id)
);
