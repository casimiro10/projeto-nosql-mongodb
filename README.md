# 🍃 E-Commerce com MongoDB + Python — NoSQL na Prática

![Python](https://img.shields.io/badge/Python-3.12-blue)
![MongoDB](https://img.shields.io/badge/MongoDB-8.0-green)
![PyMongo](https://img.shields.io/badge/PyMongo-NoSQL-orange)
![Pandas](https://img.shields.io/badge/Pandas-Analysis-yellow)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)

## 📋 Sobre o Projeto

Projeto prático de banco de dados NoSQL utilizando **MongoDB** e **Python**, desenvolvido como parte da disciplina de Banco de Dados NoSQL da Unicesumar. O projeto simula um sistema de e-commerce completo com operações CRUD, Aggregation Pipeline e análise de dados com Pandas.

---

## 🎯 Objetivo

Demonstrar na prática os conceitos de banco de dados NoSQL orientado a documentos, aplicando operações de inserção, busca, atualização, exclusão e agregação de dados utilizando MongoDB e Python.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.12**
- **MongoDB 8.0** — banco de dados NoSQL
- **MongoDB Compass** — interface gráfica
- **PyMongo** — biblioteca Python para MongoDB
- **Pandas** — análise de dados

---

## 📁 Estrutura do Projeto

```
projeto-nosql-mongodb/
│
└── projeto_mongodb.ipynb    ← Notebook completo
```

---

## 🗄️ Estrutura do Banco de Dados

```
ecommerce_db/
├── clientes      ← dados dos clientes
├── produtos      ← catálogo de produtos
└── pedidos       ← histórico de pedidos
```

---

## ⚙️ Etapas do Projeto

### 1. 🔌 Conexão com MongoDB
Conexão ao banco local via PyMongo em `mongodb://localhost:27017/`

### 2. 📝 INSERT — Inserindo Documentos
```python
clientes.insert_many(clientes_data)
produtos.insert_many(produtos_data)
```

### 3. 🔍 FIND — Buscando Documentos
```python
clientes.find()                    # todos os clientes
clientes.find({"estado": "SP"})   # filtro por estado
clientes.find_one({"nome": "..."}) # busca específica
```

### 4. ✏️ UPDATE — Atualizando Documentos
```python
clientes.update_one(
    {"nome": "Pedro Costa"},
    {"$set": {"cidade": "Florianópolis"}}
)
```

### 5. 🗑️ DELETE — Deletando Documentos
```python
clientes.delete_one({"nome": "Pedro Costa"})
```

### 6. 📊 AGGREGATION PIPELINE
```python
pipeline = [
    {"$group": {
        "_id": "$cliente",
        "total_gasto": {"$sum": "$valor"}
    }},
    {"$sort": {"total_gasto": -1}}
]
pedidos.aggregate(pipeline)
```

### 7. 🐼 Análise com Pandas
Conversão das coleções MongoDB para DataFrame Pandas para análise estatística.

---

## 📈 Resultados

| Indicador | Valor |
|---|---|
| Total de clientes | 4 |
| Total de produtos | 4 |
| Total de pedidos | 7 |
| Ticket médio | R$ 1.045,70 |
| Maior pedido | R$ 3.200,00 |
| Total em pedidos | R$ 7.319,90 |

---

## 🔄 SQL vs MongoDB

| SQL | MongoDB |
|---|---|
| Banco de dados | Banco de dados |
| Tabela | Coleção |
| Linha | Documento |
| Coluna | Campo |
| SELECT | find() |
| INSERT | insert_one() / insert_many() |
| UPDATE | update_one() / update_many() |
| DELETE | delete_one() / delete_many() |
| GROUP BY | $group (Aggregation) |

---

## 💡 Conceitos Aplicados

- **NoSQL orientado a documentos** — armazenamento em formato BSON/JSON
- **Schema flexível** — documentos da mesma coleção podem ter campos diferentes
- **Aggregation Pipeline** — consultas avançadas e agrupamentos
- **Teorema CAP** — MongoDB é um sistema AP por padrão
- **Escalabilidade horizontal** — característica principal do NoSQL

---

## 🚀 Como Executar

1. Instala o MongoDB: `mongodb.com/try/download/community`
2. Instala as dependências:
```bash
pip install pymongo pandas
```
3. Inicia o MongoDB localmente
4. Abre o notebook `projeto_mongodb.ipynb`
5. Roda todas as células

---

## 👤 Autor

**João Casimiro**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-João%20Casimiro-blue)](https://www.linkedin.com/in/jo%C3%A3o-raphael-casimiro-de-almeida-63681a23b/)
[![GitHub](https://img.shields.io/badge/GitHub-casimiro10-black)](https://github.com/casimiro10)
