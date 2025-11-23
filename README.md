
# Ecodeed Blog — Django Backend

This repository contains the backend for the Ecodeed Blog project, built with Django and a SQL database (SQLite for development).

This project is an evolving platform intended to support blog content, online courses, and other content services. The codebase currently provides a minimal blog app (models, views, templates and migrations) and will be extended to provide user management, payments, APIs, and more.

Key goals:

- Provide a flexible content backend for blog posts and courses.
- Support user authentication and role-based access (authors, students, admins).
- Support payments and subscriptions for paid courses/content.
- Expose a clean REST API for clients (web, mobile) and support webhooks for payment providers.

## Tech stack

- Python (3.10+ recommended)
- Django (4.x recommended)
- SQLite (development), easily replaceable with PostgreSQL for production
- Templates: Django templates (templates are in `blog/templates/blog`)

## Quickstart (development)

1. Clone the repo and change directory:

```bash
git clone https://github.com/gikonyo-mwema/blog_backend_django.git
cd blog_backend_django
```

2. Create a virtual environment and activate it:

```bash
python -m venv venv
source venv/bin/activate
```

3. Install dependencies (if `requirements.txt` exists) or install Django manually:

```bash
pip install -r requirements.txt || pip install django
```

4. Apply migrations and create a superuser:

```bash
python manage.py migrate
python manage.py createsuperuser
```

5. Run the dev server:

```bash
python manage.py runserver
```

Then open `http://127.0.0.1:8000/` in your browser.

## Running tests

Run the Django test suite with:

```bash
python manage.py test
```

## Project layout (important files)

- `manage.py` — Django CLI entrypoint.
- `ecodeed_blog/` — Django project settings, URLs and WSGI/ASGI.
- `blog/` — main app (models, views, templates, migrations).
- `db.sqlite3` — development database (do not commit sensitive production DB files).

## Current status

The repository currently contains the basic blog application structure including models, views, templates and initial migrations. Many features are planned and will be implemented iteratively.

## Planned features / Roadmap

Phase 1 — Core content and users
- Blog posts: rich content, categories, tags, listing and detail views
- Course model: course metadata, lessons, and enrollment models
- Authentication: user signup/login, password reset
- Admin: improved admin views for content management

Phase 2 — Monetization and integrations
- Payments & subscriptions: Stripe/PayPal integration, one-off purchases and recurring subscriptions
- API: REST (Django REST Framework) for frontend and mobile clients
- Webhooks: payment provider webhooks and verification

Phase 3 — User experience & scale
- Comments, ratings and reviews for posts/courses
- Search and filtering (Elasticsearch or PostgreSQL full-text)
- Notifications (email and in-app)
- Deployment guides (Docker, CI/CD)

## Contributing

Contributions are welcome. Typical workflow:

1. Fork the repo and create a feature branch.
2. Add tests for new functionality.
3. Run the test suite and ensure formatting is consistent.
4. Open a pull request describing the change.

Please follow Python and Django best practices and keep changes small and focused.

## Notes for maintainers

- Add a `requirements.txt` (or `pyproject.toml`) to pin dependencies for reproducible installs.
- Switch to PostgreSQL for production and configure environment variables for secrets.
- Add CI (GitHub Actions) to run tests and linting on PRs.

## License & contact

This project does not include an explicit license file yet. Add a LICENSE if you want to publish under an open-source license.

If you have questions, reach out to the repository owner or open an issue.

