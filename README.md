# RestAPI Tasks 📝

API REST simples para gerenciamento de tasks, desenvolvida com **Laravel**.  
Projeto criado com foco em aprendizado de APIs RESTful.

---

## 🚀 Tecnologias

- PHP
- Laravel
- MySQL

---

## ⚙️ Como rodar localmente

```bash
# Clone o repositório
git clone https://github.com/mateusmendesprogrammer17/RestAPI_TASKS.git

# Entre na pasta
cd RestAPI_TASKS

# Instale as dependências
composer install

# Copie o arquivo de ambiente
cp .env.example .env

# Gere a chave da aplicação
php artisan key:generate

# Configure o banco de dados no .env
DB_DATABASE=seu_banco
DB_USERNAME=seu_usuario
DB_PASSWORD=sua_senha

# Rode as migrations
php artisan migrate

# Inicie o servidor
php artisan serve
```

Base URL: `http://localhost:8000`

---

## 🧪 Rota de Teste

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/api/test` | Verifica se a API está funcionando |

**Response:**
```json
{
  "message": "API funcionando!"
}
```

---

## 📋 Endpoints — Tasks

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/api/tasks` | Lista todas as tasks |
| GET | `/api/tasks/{id}` | Busca uma task pelo ID |
| POST | `/api/tasks` | Cria uma nova task |
| PUT | `/api/tasks/{id}` | Atualiza uma task completa |
| DELETE | `/api/tasks/{id}` | Remove uma task |

---

### GET `/api/tasks`

Retorna todas as tasks cadastradas.

**Response 200:**
```json
[
  {
    "id": 1,
    "title": "Estudar Laravel",
    "description": "Aprender a criar APIs REST",
    "status": "pendente",
    "created_at": "2025-01-01T00:00:00.000000Z",
    "updated_at": "2025-01-01T00:00:00.000000Z"
  }
]
```

---

### GET `/api/tasks/{id}`

Retorna uma task específica pelo ID.

**Response 200:**
```json
{
  "id": 1,
  "title": "Estudar Laravel",
  "description": "Aprender a criar APIs REST",
  "status": "pendente",
  "created_at": "2025-01-01T00:00:00.000000Z",
  "updated_at": "2025-01-01T00:00:00.000000Z"
}
```

---

### POST `/api/tasks`

Cria uma nova task.

**Body:**
```json
{
  "title": "Estudar Flutter",
  "description": "Aprender a consumir APIs com Dio",
  "status": "pendente"
}
```

**Response 201:**
```json
{
  "id": 2,
  "title": "Estudar Flutter",
  "description": "Aprender a consumir APIs com Dio",
  "status": "pendente",
  "created_at": "2025-01-01T00:00:00.000000Z",
  "updated_at": "2025-01-01T00:00:00.000000Z"
}
```

---

### PUT `/api/tasks/{id}`

Atualiza completamente uma task existente.

**Body:**
```json
{
  "title": "Estudar Flutter - atualizado",
  "description": "Finalizar o projeto com Dio",
  "status": "concluida"
}
```

**Response 200:**
```json
{
  "id": 2,
  "title": "Estudar Flutter - atualizado",
  "description": "Finalizar o projeto com Dio",
  "status": "concluida",
  "created_at": "2025-01-01T00:00:00.000000Z",
  "updated_at": "2025-01-01T01:00:00.000000Z"
}
```

---

### DELETE `/api/tasks/{id}`

Remove uma task pelo ID.

**Response 204:** *(sem conteúdo)*

---

## 📌 Observações

- API sem autenticação — versão de estudo
- Não há validação dos campos — versão simples intencional
- Testada no Postman e Hoppscotch

---

## 📚 Próximos passos

- [ ] Adicionar validação dos campos com Form Requests
- [ ] Adicionar autenticação com Laravel Sanctum
- [ ] Consumir esta API no Flutter com Dio
