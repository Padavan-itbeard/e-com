# 🚀 FARM Stack Template

A modern, scalable template to kickstart your full-stack web projects. This template combines FastAPI (Python), React (JavaScript), and PostgresDB, all containerized with Docker and orchestrated via Docker Compose. It’s designed for rapid development and easy deployment, with a clear structure for both backend and frontend.

Inspired by best practices and scalable architecture patterns, this template helps you build robust, production-ready web applications with:
- **FastAPI** for high-performance Python APIs
- **React** for a modern, component-based frontend
- **PostgresDB** for reliable data storage
- **Nginx** for efficient static file serving and reverse proxy
- **Docker & Docker Compose** for seamless local development and deployment

Whether you're building a prototype or a large-scale application, this template provides a solid foundation for your FARM stack projects.

---


## 📑 Table of Contents
- [🚀 FARM Stack Template](#-farm-stack-template)
  - [📑 Table of Contents](#-table-of-contents)
  - [✨ Features](#-features)
  - [� Getting Started](#-getting-started)
    - [Backend (FastAPI)](#backend-fastapi)
    - [Frontend (React)](#frontend-react)
    - [Nginx](#nginx)
  - [🚀 Deploy](#-deploy)
  - [🤝 Contribute to the Project](#-contribute-to-the-project)
  - [📬 Contact](#-contact)
- [Deploy and Host FastAPI-React-PGDB-Template on Railway](#deploy-and-host-fastapi-react-pgdb-template-on-railway)
  - [Why Railway?](#why-railway)
  - [Use Cases](#use-cases)
  - [Requirements](#requirements)


## ✨ Features

**backend/:** FastAPI backend
- **alembic/:** Alembic migrations.
- **app/:** Main FastAPI code.
  - **sample_module/**: Modular structure example
    - **schemas/:** Pydantic schemas
    - **routes/:** API routes
    - **apis.py, crud.py, exceptions.py, formatters.py, models.py, selectors.py, services.py:** Core logic
  - **common/**: Shared utilities (auth, CRUD, exceptions, pagination, schemas, security, types, utils)
  - **core/**: Database, handlers, settings, tags
  - **external/**: External integrations

**frontend/:** React app
- **public/:** Static assets
- **src/:** Components, logic, tests

**nginx/:** Production Nginx config

**Other:**
- **.vscode/:** VS Code config
- **tests/:** Backend tests
- **env_sample.txt:** Env example
- **.flake8, .gitignore, .pylintrc:** Lint/config
- **alembic.ini, docker-compose.yml, Dockerfile, LICENSE, pytest.ini, railway.toml, requirements.txt, start.sh:** Project config

## 💡 Getting Started

### Backend (FastAPI)
1. Create a virtual environment (if not using Docker):
   ```shell
   py -m venv .venv
   .venv\Scripts\activate  # Windows
   source .venv/bin/activate  # macOS/Linux
   ```
2. Install dependencies:
   ```shell
   pip install -r requirements.txt
   ```
   Or use Docker Compose:
   ```shell
   docker compose up
   ```
3. Copy `.env_sample` to `.env` and update variables.
4. Run migrations:
   ```shell
   alembic upgrade head
   ```
5. Start FastAPI:
   ```shell
   fastapi dev  # Dev
   fastapi run  # Prod
   ```

### Frontend (React)
1. In `frontend/`:
   ```shell
   npm install
   npm start
   ```
   Visit `http://localhost:3000`.
2. Build for production:
   ```shell
   npm run build
   ```

### Nginx
- Use `nginx/nginx.conf` to serve the frontend and proxy API requests.
- Example Docker run:
  ```shell
  docker run --name my-nginx -v /path/to/nginx.conf:/etc/nginx/nginx.conf:ro -v /path/to/frontend/build:/usr/share/nginx/html:ro -p 80:80 -d nginx
  ```

## 🚀 Deploy

Deploy on Railway:

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/xkVPKc?referralCode=uBTGZq)

---


## 🤝 Contribute to the Project

We welcome contributions from the community to make this FARD Starter Template even better. If you have ideas for improvements, new features, or bug fixes, feel free to:

- Fork the repository and create a new branch.
- Submit a Pull Request with your changes.
- Engage in discussions on ideas, enhancements, or fixes.

By contributing, you help make this template more valuable for developers building FastAPI applications. Together, we can create a robust foundation for large-scale projects. Thank you for your support!

For additional information, refer to the following resources:

- FastAPI documentation: https://fastapi.tiangolo.com/
- Alembic documentation: https://alembic.sqlalchemy.org/en/latest/
- Django Structure for Scale lecture: https://youtu.be/yG3ZdxBb1oo?si=D6A9dHyhKb_Kf-J7


## 📬 Contact

Feel free to reach out if you have questions or suggestions.

- Name: Abdulrahim Kasim
- Email: ikasima0@gmail.com
- GitHub: github.com/lNameless


---


# Deploy and Host FastAPI-React-PGDB-Template on Railway

A production-ready starter kit for full-stack apps: FastAPI backend, React frontend, PGDB database, all with Docker Compose. Designed for fast development, scalability, and easy cloud deployment.

## Why Railway?
Railway hosts your stack with minimal setup and easy scaling. Deploy servers, databases, and more in one place.

## Use Cases
- SaaS prototyping
- Modern API + UI projects
- Learning/hackathons

## Requirements
- Docker & Docker Compose
- Railway account

---

Happy coding! 🚀