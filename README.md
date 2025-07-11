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
  - [📁 Project Structure](#-project-structure)
  - [💡 Getting Started](#-getting-started)
    - [Backend (FastAPI)](#backend-fastapi)
    - [Frontend (React)](#frontend-react)
    - [Nginx (Production Reverse Proxy)](#nginx-production-reverse-proxy)
  - [🛠️ Using auto-module.py](#️-using-auto-modulepy)
    - [To create a new module, simply run:](#to-create-a-new-module-simply-run)
  - [🎗 License](#-license)
  - [🚀 Deploy](#-deploy)
  - [🤝 Contribute to the Project](#-contribute-to-the-project)
  - [📬 Contact](#-contact)
- [Deploy and Host FastAPI-React-MongoDB-Template on Railway](#deploy-and-host-fastapi-react-mongodb-template-on-railway)
  - [About Hosting FastAPI-React-MongoDB-Template](#about-hosting-fastapi-react-mongodb-template)
  - [Why Deploy FastAPI-React-MongoDB-Template on Railway?](#why-deploy-fastapi-react-mongodb-template-on-railway)
  - [Common Use Cases](#common-use-cases)
  - [Dependencies for FastAPI-React-MongoDB-Template Hosting](#dependencies-for-fastapi-react-mongodb-template-hosting)
    - [Deployment Dependencies](#deployment-dependencies)


## ✨ Features

**backend/:** The main FastAPI application directory
- **alembic/:** Contains Alembic settings and migrations.
- **app/:** The main FastAPI project directory.
  - **sample_module/**: Example structure for modular design, allowing easy decoupling
    - **schemas/:** Contains structured schemas used across the app.
    - **routes/:** Contains route definitions and handlers.
    - **apis.py:**  Stores all API route definitions.
    - **crud.py:** Contains CRUD operations.
    - **exceptions.py:** Stores custom exceptions.
    - **formatters.py:** Holds formatting functions.
    - **models.py:** Defines database models
    - **selectors.py:** Handles data retrieval operations.
    - **services.py:** Manages data modification operations (POST, PUT, DELETE).
  
  - **common/**: Contains shared utilities and general functionalities. 
    - **annotations.py:**  Stores custom type annotations.
    - **auth.py:** Manages authentication.
    - **crud.py:** Where all the general/generic CRUD classes will be kept.
    - **dependencies.py:** Defines dependencies used across modules.
    - **exceptions.py:** Where all the general/generic exceptions are kept.
    - **paginators.py:** Collection of helpers for response pagination.
    - **schemas.py:** Where you will keep your general/generic schemas.
    - **security.py:** Where all the security functions are kept.
    - **types.py:** Contains common types used in the application.
    - **utils.py:** General utility functions.
  
  - **core/**: Core functionalities of the application.
    - **database.py:** Database connection and session management.
    - **handlers.py:** Exception handlers.
    - **settings.py:** Environment configuration settings.
    - **tags.py:** Route tags.
  
  - **external/**: External dependencies and request handling.
    - **_request.py:** Request handling utilities.
 
**frontend/:** React-based frontend application
  - **public/:** Static assets and HTML template
  - **src/:** Source code for the React application
    - Component files (*.js, *.css)
    - Todo list implementation
    - Testing setup

**nginx/:** Nginx configuration for production deployment
  - **nginx.conf:** Nginx server configuration

**Other Configuration Files:**
- **.vscode/:** Configuration files for Visual Studio Code.
- **tests/:** Houses all application tests.
- **env_sample.txt:** Sample environment variables.
- **.flake8:** Contains the configurations for flake8.
- **.gitignore:** Specifies which folders/files to not push to github.
- **.pylintrc:** Contains the configurations for pylint.
- **alembic.ini:** Contains all the configurations for Alembic.
- **docker-compose.yml:** Docker configurations for containerized setup.
- **Dockerfile:** Instructions to build docker image.
- **LICENSE:** License details.
- **pytest.ini:** Where all the pytest configurations will be kept.
- **railway.toml:** Contains all the railway configurations.
- **requirements.txt:** Lists all application dependencies.
- **start.sh:** Application start up processes.


## 📁 Project Structure

```plaintext
.vscode
backend/
    alembic/
    app/
        sample_module/
            schemas/
              __init__.py
              base.py
              create.py
              edit.py
              response.py
            routes/
              __init__.py
              base.py
            __init__.py
            apis.py
            crud.py
            exceptions.py
            formatters.py
            models.py
            selectors.py
            services.py
        common/
            __init__.py
            annotations.py
            auth.py
            crud.py
            dependencies.py
            exceptions.py
            paginators.py
            schemas.py
            security.py
            types.py
            utils.py
        core/
            __init__.py
            database.py
            handlers.py
            settings.py
            tags.py
        external/
            __init__.py
            _request.py
        __init__.py
        main.py
    tests/
        __init__.py
    alembic.ini
    auto-module.py
    docker-compose.yml
    Dockerfile
    pytest.ini
    requirements.txt
frontend/
    public/
        favicon.ico
        index.html
        logo192.png
        logo512.png
        manifest.json
        robots.txt
    src/
        App.css
        App.js
        App.test.js
        index.css
        index.js
        ListTodoLists.css
        ListTodoLists.js
        logo.svg
        reportWebVitals.js
        setupTests.js
        ToDoList.css
        ToDoList.js
    package.json
    README.md
nginx/
    nginx.conf
.env_sample
.flake8
.gitignore
.pylintrc
LICENSE
railway.toml
README.md
start.sh
```


## 💡 Getting Started

### Backend (FastAPI)
1. Set up Virtual Environment (if you are not using Docker)

   ```shell
   py -m venv .venv
   .venv\Scripts\activate  # Windows
   source .venv/bin/activate  # macOS/Linux
   ```

2. Install Dependencies:
   Local install

   ```shell
   pip install -r requirements.txt
   ```
   Or with Docker

   ```shell
   docker compose up
   ```

3. Create a `.env` file and add environment variables (use .env_sample as a guide).

4. Initialize Database Tables
   ```shell
   alembic upgrade head
   ```

5. Start the Application
   Development Mode:
   ```shell
   fastapi dev
   ```
   Production Mode:
   ```shell
   fastapi run
   ```

6. Test the application by making requests to the endpoints.

---

### Frontend (React)
1. Navigate to the `frontend` directory:
   ```shell
   cd frontend
   ```
2. Install dependencies:
   ```shell
   npm install
   ```
3. Start the development server:
   ```shell
   npm start
   ```
   The app will be available at `http://localhost:3000` by default.

4. To build for production:
   ```shell
   npm run build
   ```
   The production-ready files will be in the `frontend/build` directory.

---

### Nginx (Production Reverse Proxy)
- The `nginx/nginx.conf` file provides a sample configuration for serving the frontend (React build) and proxying API requests to the FastAPI backend.
- To use Nginx in production:
  1. Make sure you have built the frontend (`npm run build`).
  2. Ensure your FastAPI backend is running (see above).
  3. Use Docker or your own Nginx installation to serve the static files and reverse proxy API requests. Example Docker usage:
     ```shell
     docker run --name my-nginx -v /path/to/your/project/nginx/nginx.conf:/etc/nginx/nginx.conf:ro -v /path/to/your/project/frontend/build:/usr/share/nginx/html:ro -p 80:80 -d nginx
     ```
  4. Adjust the Nginx config as needed for your deployment environment.

---


## 🛠️ Using auto-module.py
The auto-module.py script automates the creation of new FastAPI modules, saving you time and ensuring consistency. It generates the following structure for a new module:
```bash
app/
└── ModuleName/
    ├── routes/
    │   ├── __init__.py
    │   ├── base.py
    ├── schemas/
    │   ├── __init__.py
    │   ├── base.py
    │   ├── create.py
    │   ├── edit.py
    │   ├── response.py
    ├── __init__.py
    ├── apis.py
    ├── models.py
    ├── services.py
    ├── selectors.py
    ├── exceptions.py
    └── formatters.py
```
### To create a new module, simply run:
```bash
python auto-module.py
```
Follow the prompts to specify the module name, and the script will handle the rest.


## 🎗 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## 🚀 Deploy
YOU CAN DIRECTLY DEPLOY YOUR OWN VERSION USING THE LINK BELOW 

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/Gh2dUD?referralCode=uBTGZq)

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


# Deploy and Host FastAPI-React-MongoDB-Template on Railway

FastAPI-React-MongoDB-Template is a modern, production-ready starter kit for building full-stack web applications. It combines FastAPI for the backend, React for the frontend, and MongoDB for data storage, all orchestrated with Docker and Docker Compose. This template is designed for rapid development, scalability, and easy deployment to cloud platforms like Railway.

## About Hosting FastAPI-React-MongoDB-Template

Hosting FastAPI-React-MongoDB-Template involves deploying a containerized full-stack application that integrates a high-performance FastAPI backend, a dynamic React frontend, and a robust MongoDB database. With Docker Compose, all services are managed together, simplifying both local development and cloud deployment. Railway provides a seamless platform to deploy, scale, and manage your application and its dependencies, reducing operational overhead and accelerating your go-to-production timeline.

## Why Deploy FastAPI-React-MongoDB-Template on Railway?

<!-- Recommended: Keep this section as shown below -->
Railway is a singular platform to deploy your infrastructure stack. Railway will host your infrastructure so you don't have to deal with configuration, while allowing you to vertically and horizontally scale it.

By deploying FastAPI-React-MongoDB-Template on Railway, you are one step closer to supporting a complete full-stack application with minimal burden. Host your servers, databases, AI agents, and more on Railway.
<!-- End recommended section -->

## Common Use Cases

- Rapid prototyping of SaaS products
- Building scalable APIs with modern UIs
- Educational projects and hackathons

## Dependencies for FastAPI-React-MongoDB-Template Hosting

- Docker & Docker Compose
- Railway account

### Deployment Dependencies

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [React Documentation](https://react.dev/)
- [MongoDB Documentation](https://www.mongodb.com/docs/)
- [Railway Documentation](https://docs.railway.app/)

---

Happy coding! 🚀