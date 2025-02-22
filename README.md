# ☕ Cafe & Wifi API

![Cafe & Wifi API](https://img.shields.io/badge/API-Flask-blue) ![Database](https://img.shields.io/badge/Database-SQLite-green) ![License](https://img.shields.io/badge/License-MIT-pink)

Bem-vindo à **Cafe & Wifi API**, um serviço simples para gerenciar informações sobre cafés, incluindo localização, preço do café, disponibilidade de Wi-Fi, tomadas e outras características.

---

##  Visão Geral 👁
Esta API permite recuperar dados de cafés cadastrados, além de adicionar, atualizar e remover informações de forma prática.

### ✨ Funcionalidades:
- Buscar todos os cafés cadastrados
- Encontrar um café por localização
- Obter um café aleatório
- Adicionar novos cafés
- Atualizar o preço do café
- Remover cafés do banco de dados
  
---

## 📌 Instalação
Clone este repositório e instale as dependências:

```sh
pip install -r requirements.txt
```

Após isso, execute a API com o comando:

```sh
python main.py
```

A API estará disponível em **http://127.0.0.1:5000/**

---

## 📂 Endpoints Disponíveis

### 🔹 `GET /random`
Retorna um café aleatório.

**Exemplo de Resposta:**
```json
{
  "cafe": {
    "id": 1,
    "name": "Café do Centro",
    "location": "Brasília",
    "coffee_price": "R$5,00"
  }
}
```

### 🔹 `GET /search/<location>`
Retorna cafés disponíveis em uma determinada localização.

**Exemplo:** `/search/Brasília`

**Exemplo de Resposta:**
```json
{
  "cafes": [
    {
      "id": 1,
      "name": "Café do Centro",
      "location": "Brasília",
      "coffee_price": "R$5,00"
    }
  ]
}
```

### 🔹 `GET /all`
Retorna todos os cafés cadastrados.

### 🔹 `POST /add`
Adiciona um novo café.

**Parâmetros (Form-Data):**
- `name`: Nome do café (obrigatório)
- `map_url`: URL do mapa
- `img_url`: URL da imagem
- `location`: Localização (obrigatório)
- `has_sockets`, `has_toilet`, `has_wifi`, `can_take_calls`: `true` ou `false`
- `seats`: Número de assentos
- `coffee_price`: Preço do café

### 🔹 `PATCH /update-price/<int:cafe_id>`
Atualiza o preço do café com ID especificado.

### 🔹 `DELETE /report-closed/<int:cafe_id>`
Remove um café do banco de dados, se a `api_key` correta for fornecida.


---

💖 Feito com carinho por [gus-ant](https://github.com/gus-ant)! 😊

