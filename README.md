# SQL-Fundamentals-Project

# Sistema de Gerenciamento Logístico

Este projeto implementa um sistema de gerenciamento logístico utilizando banco de dados SQL. Ele é projetado para gerenciar motoristas, veículos, rotas, viagens, clientes e entregas, garantindo integridade e eficiência no controle de dados relacionados.

---

## **Estrutura do Projeto**

O repositório contém dois arquivos principais:

- **estrutura.sql**: Script para criação das tabelas, restrições, e configuração do usuário e tablespace.
- **dados.sql**: Script para inicialização do banco de dados com dados de exemplo.

---

## **Requisitos**

- **Banco de Dados:** Oracle Database (ou outro que suporte a sintaxe utilizada).
- **Permissões:** O usuário deve ter permissões para criar tabelas, tablespaces e gerenciar dados.

---

## **Configuração**

1. **Criação do Usuário e Tablespace**
   - Execute o trecho inicial do arquivo `estrutura.sql` para configurar o usuário `grupo_6` e o tablespace `USR_LOGISTICA`.

2. **Criação das Tabelas**
   - Execute o restante do arquivo `estrutura.sql` para criar as tabelas necessárias para o sistema.

3. **Inicialização dos Dados**
   - Execute o arquivo `dados.sql` para inserir dados de exemplo nas tabelas criadas.

---

## **Estrutura das Tabelas**

As principais tabelas do sistema incluem:

1. **MOTORISTAS**: Armazena informações sobre os motoristas.
2. **VEICULOS**: Armazena informações sobre os veículos utilizados.
3. **ROTAS**: Detalha as rotas de origem e destino.
4. **VIAGENS**: Relaciona motoristas, veículos e rotas com informações adicionais de data e status.
5. **CLIENTES**: Armazena os dados dos clientes.
6. **ENTREGAS**: Relaciona viagens a entregas realizadas.

---

## **Dados de Exemplo**

Os dados inseridos no arquivo `dados.sql` incluem:

- **Motoristas:** 5 registros com nome, CNH e telefone.
- **Veículos:** 5 registros com placa, modelo, capacidade de carga e status.
- **Rotas:** 5 registros com origem, destino e distância.
- **Viagens:** 5 registros associando motoristas, veículos e rotas.
- **Clientes:** 5 registros com informações de contato e endereço.
- **Entregas:** 5 registros vinculando viagens e clientes.

---

## **Como Executar**

1. Conecte-se ao banco de dados como administrador.
2. Execute o arquivo `estrutura.sql` para configurar o schema e criar as tabelas.
3. Execute o arquivo `dados.sql` para inserir os dados iniciais.
4. Use comandos SQL para manipular e consultar os dados conforme necessário.

---

## **Exemplo de Consulta**

**Consultar todas as entregas com status "Pendente":**
```sql
SELECT 
  ENTREGAS.ENTREGA_ID, 
  CLIENTES.NOME AS CLIENTE, 
  ENTREGAS.ENDERECO_ENTREGA 
FROM 
  ENTREGAS
JOIN 
  CLIENTES ON ENTREGAS.CLIENTE_ID = CLIENTES.CLIENTE_ID
WHERE 
  ENTREGAS.STATUS = 'Pendente';
