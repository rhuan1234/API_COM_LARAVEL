# 📺 Gerenciador de Séries

Uma aplicação web desenvolvida com **Laravel 9** para gerenciar séries de TV, temporadas e episódios. O projeto implementa boas práticas de desenvolvimento como padrão Repository, eventos e listeners.

## 🎯 Características Principais

- ✅ Autenticação de usuários com Laravel Breeze
- ✅ CRUD completo para séries, temporadas e episódios
- ✅ API RESTful com hypermedia links
- ✅ Sistema de eventos e listeners
- ✅ Envio de emails automatizado
- ✅ Design responsivo com Tailwind CSS e Bootstrap
- ✅ Padrão Repository para camada de dados
- ✅ Validações de dados

## 🛠️ Tecnologias Utilizadas

- **Backend**: Laravel 9.2
- **Frontend**: Tailwind CSS 3, Alpine.js 3, Bootstrap 5
- **Banco de Dados**: SQLite/MySQL
- **Build Tool**: Laravel Mix
- **Autenticação**: Laravel Breeze
- **Testing**: PHPUnit
- **Ferramentas de Dev**: Laravel Debugbar, Tinker

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- **PHP 8.1+** - [Download](https://www.php.net/downloads)
- **Composer** - [Download](https://getcomposer.org/)
- **Node.js 14+** - [Download](https://nodejs.org/)
- **Git** - [Download](https://git-scm.com/)

## 🚀 Instalação e Configuração

### 1. Clonar o Repositório
```bash
git clone https://github.com/rhuan1234/API_COM_LARAVEL
cd API_COM_LARAVEL
```

### 2. Instalar Dependências PHP
```bash
composer install
```

### 3. Instalar Dependências Node.js
```bash
npm install
```

### 4. Configurar o Arquivo .env
```bash
cp .env.example .env
```

Edite o arquivo `.env` com suas configurações:
```env
APP_NAME="Gerenciador de Séries"
APP_ENV=local
APP_DEBUG=true
APP_URL=http://localhost:8000

DB_CONNECTION=sqlite
# ou para MySQL:
# DB_CONNECTION=mysql
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=series_db
# DB_USERNAME=root
# DB_PASSWORD=

MAIL_DRIVER=smtp
MAIL_HOST=seu-smtp-host
MAIL_PORT=587
MAIL_USERNAME=seu-email
MAIL_PASSWORD=sua-senha
MAIL_FROM_ADDRESS=seu-email@example.com
```

### 5. Gerar Chave da Aplicação
```bash
php artisan key:generate
```

### 6. Executar Migrations
```bash
php artisan migrate
```

### 7. Compilar Assets (CSS/JS)
```bash
npm run dev
```

Para produção:
```bash
npm run production
```

## 🎮 Executando a Aplicação

### Servidor de Desenvolvimento
```bash
php artisan serve
```

A aplicação estará disponível em `http://localhost:8000`

### Modo Watch (Recompila assets automaticamente)
```bash
npm run watch
```

### Modo Hot (Hot Module Replacement)
```bash
npm run hot
```

## 📁 Estrutura do Projeto

```
app/
├── Http/
│   ├── Controllers/      # Controladores da aplicação
│   ├── Middleware/       # Middleware customizado
│   └── Requests/         # Form Requests validação
├── Models/
│   ├── Series.php        # Modelo de Séries
│   ├── Season.php        # Modelo de Temporadas
│   ├── Episode.php       # Modelo de Episódios
│   └── User.php          # Modelo de Usuários
├── Events/
│   └── SeriesCreated.php # Evento quando série é criada
├── Listeners/            # Listeners para eventos
├── Mail/
│   └── SeriesCreated.php # Mailable para envio de emails
└── Repositories/         # Padrão Repository

resources/
├── views/                # Templates Blade
├── css/                  # Estilos (Tailwind)
└── js/                   # Scripts JavaScript (Alpine.js)

routes/
├── web.php               # Rotas web
└── api.php               # Rotas API

database/
├── migrations/           # Migrations do banco
└── seeders/              # Seeds para dados iniciais

tests/
├── Feature/              # Testes de funcionalidade
└── Unit/                 # Testes unitários
```

## 🔌 API Endpoints Principais

- `GET /api/series` - Listar todas as séries
- `GET /api/series/{id}` - Obter série específica
- `GET /api/series/{id}/seasons` - Listar temporadas da série
- `GET /api/series/{id}/episodes` - Listar episódios da série
- `POST /api/series` - Criar nova série
- `PUT /api/series/{id}` - Atualizar série
- `DELETE /api/series/{id}` - Deletar série

```


```

### Executar migrations
```bash
php artisan migrate
```




## 🌱 Seeders

### Executar seeders
```bash
php artisan db:seed
```

### Executar seeder específico
```bash
php artisan db:seed --class=DatabaseSeeder
```

## 🐛 Debugging

A aplicação inclui **Laravel Debugbar** para facilitar o debug:

- Disponível em `http://localhost:8000` (canto inferior direito)
- Mostra queries, requisições, variáveis, etc.

Para acessar o Laravel Tinker (REPL):
```bash
php artisan tinker
```

## 📚 Estrutura de Modelos

### Series
- `id`: ID único
- `nome`: Nome da série
- `cover`: URL da capa
- `timestamps`: created_at, updated_at

### Seasons
- `id`: ID único
- `series_id`: Relacionamento com Series
- `numero`: Número da temporada
- `timestamps`: created_at, updated_at

### Episodes
- `id`: ID único
- `season_id`: Relacionamento com Seasons
- `numero`: Número do episódio
- `timestamps`: created_at, updated_at

## 🎓 Conceitos Implementados

- **Padrão Repository**: Abstração da camada de dados
- **Eloquent ORM**: Relacionamentos entre modelos
- **Events & Listeners**: Sistema de eventos desacoplado
- **Validações**: Form Requests
- **Autenticação**: Laravel Breeze
- **API RESTful**: Com hypermedia links
- **Migrations**: Versionamento do banco de dados

## 🚀 Deploy

### Em Produção (Heroku, DigitalOcean, etc.)

1. Configure variáveis de ambiente
2. Execute migrations: `php artisan migrate --force`
3. Cache configurações: `php artisan config:cache`
4. Compile routes: `php artisan route:cache`
5. Compile views: `php artisan view:cache`

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

Desenvolvido como projeto de aprendizado Laravel.

## 📞 Suporte

Para dúvidas e problemas, abra uma issue no repositório.

---


