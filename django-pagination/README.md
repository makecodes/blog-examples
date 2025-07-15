# Django Pagination Example

A Django REST API project demonstrating pagination implementation with a simple blog system.

## 📋 Overview

This project showcases how to implement pagination in Django REST Framework using a blog application with categories and posts. It's designed as a learning resource for developers who want to understand pagination patterns in Django applications.

## 🚀 Features

- **Blog Models**: Simple blog system with Categories and Posts
- **Django REST Framework**: RESTful API implementation
- **Pagination Ready**: Structured for pagination examples
- **Modern Python**: Built with Python 3.12+
- **UV Package Manager**: Fast Python package management

## 🏗️ Project Structure

```
django-pagination/
├── app/                    # Main Django project settings
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py         # Django configuration
│   ├── urls.py             # Main URL routing
│   └── wsgi.py
├── blog/                   # Blog application
│   ├── __init__.py
│   ├── admin.py            # Django admin configuration
│   ├── apps.py             # App configuration
│   ├── models.py           # Category and Post models
│   ├── serializers.py      # DRF serializers
│   ├── views.py            # API views (to be implemented)
│   └── migrations/         # Database migrations
├── manage.py               # Django management script
├── Makefile               # Development commands
├── pyproject.toml         # Project dependencies and configuration
├── uv.lock               # Locked dependencies
└── README.md             # This file
```

## 📦 Models

### Category Model
- `name`: Unique category name (max 100 characters)

### Post Model
- `title`: Post title (max 200 characters)
- `content`: Post content (TextField)
- `created_at`: Auto-generated creation timestamp
- `updated_at`: Auto-updated modification timestamp
- `category`: Foreign key relationship to Category

## 🛠️ Technologies Used

- **Django 5.2.4+**: Web framework
- **Django REST Framework 3.16.0+**: API framework
- **Python 3.12+**: Programming language
- **UV**: Fast Python package manager
- **Ruff**: Python linter and formatter
- **SQLite**: Default database (development)

## 🚦 Getting Started

### Prerequisites

- Python 3.12 or higher
- UV package manager

### Installation

1. **Clone the repository:**
   ```bash
   git clone git@github.com:makecodes/blog-examples.git
   cd django-pagination
   ```

2. **Install dependencies:**
   ```bash
   uv sync --dev
   ```

3. **Run migrations:**
   ```bash
   make migrate
   ```

4. **Start the development server:**
   ```bash
   make run
   ```

The application will be available at `http://localhost:8000/`

## 🎯 Available Commands

The project includes a `Makefile` with convenient commands:

| Command | Description |
|---------|-------------|
| `make help` | Displays this help message |
| `make run` | Starts the Django development server |
| `make migrate` | Applies Django migrations |
| `make makemigrations` | Creates new Django migrations |
| `make shell` | Opens the Django interactive shell (shell_plus) |
| `make show_urls` | Displays all Django routes/URLs |
| `make lint` | Runs the formatter and linter (ruff) |
| `make fix-lint` | Automatically fixes lint issues |
| `make clean` | Removes temporary cache and build files |

## 🔧 Development

### Code Quality

This project uses **Ruff** for code formatting and linting:

```bash
make lint        # Check code quality
make fix-lint    # Auto-fix issues
```

### Database Management

```bash
make makemigrations  # Create new migrations
make migrate         # Apply migrations
make shell          # Access Django shell
```

## 📊 Pagination Implementation

This project is structured to demonstrate various pagination techniques:

- **Limit/Offset Pagination**: Traditional page-based pagination
- **Cursor Pagination**: For large datasets with consistent ordering
- **Page Number Pagination**: User-friendly page navigation

*(Implementation details to be added in views.py)*

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Run tests and linting: `make lint`
5. Commit your changes: `git commit -am 'Add feature'`
6. Push to the branch: `git push origin feature-name`
7. Submit a pull request

## 📝 License

This project is intended for educational purposes. Feel free to use it as a reference for learning Django pagination techniques.

## 🔗 Related Resources

- [Django REST Framework Pagination](https://www.django-rest-framework.org/api-guide/pagination/)
- [Django Documentation](https://docs.djangoproject.com/)
- [UV Package Manager](https://github.com/astral-sh/uv)

---

**Note**: This is a demonstration project for learning pagination in Django. The views and URL configurations are ready to be implemented with pagination examples.
