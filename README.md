# 🚂 rails-init

A clean and ready-to-use **Ruby on Rails boilerplate** — pre-configured with Docker, RuboCop, GitHub Actions CI, and a standard MVC structure. Clone, configure, and ship.

---

## 📋 Description

**rails-init** is a minimal yet opinionated Rails starter template designed to save you setup time. It provides a solid foundation for new web applications with best practices already baked in:

- **Dockerized** environment for consistent local development and production deployment
- **RuboCop** configured for code style enforcement
- **GitHub Actions** CI pipeline ready out of the box
- Standard Rails MVC architecture with all default directories in place

---

## 🛠️ Tech Stack

| Layer         | Technology                        |
|---------------|-----------------------------------|
| Language      | Ruby (see `.ruby-version`)        |
| Framework     | Ruby on Rails                     |
| Containerization | Docker + `.dockerignore`       |
| Linting       | RuboCop (`.rubocop.yml`)          |
| CI/CD         | GitHub Actions (`.github/`)       |
| Testing       | Rails default test suite          |
| Asset pipeline | Sprockets / Propshaft             |

---

## 🗂️ Project Structure

```
rails-init/
├── .github/            # GitHub Actions CI workflows
├── app/                # MVC core (models, views, controllers, helpers, assets)
├── bin/                # Executable scripts (rails, bundle, setup, dev…)
├── config/             # App configuration (routes, database, environments…)
├── db/                 # Database schema and migrations
├── lib/                # Custom tasks and extensions
├── log/                # Application logs
├── public/             # Static files served directly
├── storage/            # Active Storage files (uploads, attachments)
├── test/               # Test suite
├── tmp/                # Temporary files (cache, pids, sockets)
├── vendor/             # Third-party code
├── .dockerignore       # Files excluded from Docker build context
├── .rubocop.yml        # RuboCop linting configuration
├── .ruby-version       # Ruby version pin
├── Dockerfile          # Production-ready Docker image
├── Gemfile             # Ruby gem dependencies
└── Rakefile            # Rake task definitions
```

---

## 🚀 Getting Started

### Prerequisites

- [Ruby](https://www.ruby-lang.org/) — version specified in `.ruby-version`
- [Bundler](https://bundler.io/)
- [Docker](https://www.docker.com/) *(optional but recommended)*
- A database (SQLite / PostgreSQL / MySQL depending on your config)

---

### Option A — Local setup

#### 1. Clone the repository

```bash
git clone https://github.com/yannisduvignau/rails-init.git
cd rails-init
```

#### 2. Install dependencies

```bash
bundle install
```

#### 3. Setup the database

```bash
bin/rails db:create db:migrate
```

#### 4. Start the server

```bash
bin/rails server
```

The app will be available at → [http://localhost:3000](http://localhost:3000)

---

### Option B — Docker setup

#### 1. Build the image

```bash
docker build -t rails-init .
```

#### 2. Run the container

```bash
docker run -d -p 3000:3000 \
  -e RAILS_MASTER_KEY=$(cat config/master.key) \
  --name rails-app rails-init
```

The app will be available at → [http://localhost:3000](http://localhost:3000)

---

## ✅ Running Tests

```bash
bin/rails test
```

Or run a specific test file:

```bash
bin/rails test test/models/user_test.rb
```

---

## 🧹 Linting

This project uses [RuboCop](https://rubocop.org/) for code style enforcement.

```bash
# Check for offenses
bundle exec rubocop

# Auto-fix safe offenses
bundle exec rubocop -a
```

---

## ⚙️ CI/CD

GitHub Actions workflows are located in `.github/`. They run automatically on push and pull requests, covering:

- Dependency installation
- Test suite execution
- RuboCop linting

---

## 🔧 Configuration

| File | Purpose |
|------|---------|
| `config/database.yml` | Database connection settings |
| `config/credentials.yml.enc` | Encrypted secrets (edit with `bin/rails credentials:edit`) |
| `config/environments/` | Per-environment configuration (development, test, production) |
| `.ruby-version` | Ruby version used by rbenv / rvm / asdf |

---

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## 👤 Author

**Yannis Duvignau**  
[GitHub](https://github.com/yannisduvignau)

---

## 📄 License

This project is distributed under an open license. See the `LICENSE` file for more details.