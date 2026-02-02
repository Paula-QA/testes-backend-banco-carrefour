# 🧪 Testes Automatizados de Back-end – Banco Carrefour

Este repositório contém testes automatizados de **API (Back-end)** desenvolvidos no **Postman**, como parte de um desafio técnico.  
O foco está na **validação de qualidade**, **cobertura funcional**, **cenários positivos e negativos** e **execução reprodutível**.

---

## 🎯 Objetivo

Validar o fluxo completo de **gestão de usuários e autenticação**, garantindo o correto funcionamento da API por meio de testes automatizados e encadeados, sem dependência de dados estáticos.

---

## 🛠️ Tecnologias e Ferramentas

- Postman  
- JavaScript (scripts de teste)  
- API REST  
- Variáveis de ambiente  
- Collection Runner / Newman  

---

## 📂 Estrutura do Repositório


---

## 🔄 Estratégia de Testes

- O usuário é **criado dinamicamente**
- O **ID**, **email** e **senha** são armazenados em variáveis de ambiente
- Esses dados são reutilizados nos testes de:
  - login
  - consulta
  - edição
  - exclusão
- A estratégia garante:
  - reexecução segura
  - independência de dados fixos
  - validação de ponta a ponta

---

## 🧪 Cenários Cobertos

### 🔹 Usuário
- Criação de usuário  
- Consulta de usuário por ID  
- Validação da criação  
- Edição de usuário  
- Validação da edição  
- Exclusão de usuário  
- Validação da exclusão  

### 🔹 Login – Cenários Positivos
- Login realizado com sucesso com usuário criado dinamicamente  

### 🔹 Login – Cenários Negativos
- Login com senha inválida  
- Login com e-mail inexistente  
- Login sem e-mail  
- Login sem senha  

---

## 🌱 Environment do Postman

O projeto utiliza um **environment versionado** para armazenar variáveis dinâmicas e garantir a correta execução dos testes.

### Variáveis utilizadas

| Variável | Descrição |
|--------|----------|
| `carrefour_api` | URL base da API |
| `userId` | ID do usuário criado |
| `loginEmail` | Email do usuário criado |
| `loginPassword` | Senha do usuário |
| `token` | Token de autenticação |
| `userCounter` | Contador para geração de dados únicos |
| `userSuffix` | Sufixo numérico para evitar duplicidade |

📌 O environment **não contém dados sensíveis** e pode ser versionado com segurança.

---

## ▶️ Como Executar os Testes

### Via Postman
1. Importar a collection  
2. Importar o environment `Carrefour Variables`  
3. Selecionar o environment no Postman  
4. Executar a collection via **Collection Runner**  

### Via Newman
```bash
newman run collections/Testes-de-Back-end-Banco-Carrefour.postman_collection.json \
-e environments/Carrefour-Variables.postman_environment.json

