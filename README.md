# Django Blog

A simple blog application built with Django. Features:

- List, view, create, edit, and delete blog posts
- User signup, login, and logout (Django's built-in auth)
- Comments on posts (logged-in users only)
- Auto-generated slugs for post URLs
- Django admin for managing posts and comments
- Bootstrap 5 styling (via CDN, no build step needed)

## Project structure

```
blogproject/
├── manage.py
├── requirements.txt
├── blogproject/        # project settings, urls, wsgi/asgi
└── blog/               # the blog app: models, views, templates
```

## Local setup

1. **Create and activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run migrations**

   ```bash
   python manage.py migrate
   ```

4. **Create an admin user** (so you can log in and create posts)

   ```bash
   python manage.py createsuperuser
   ```

5. **Run the dev server**

   ```bash
   python manage.py runserver
   ```

6. Visit `http://127.0.0.1:8000/` for the blog, or `http://127.0.0.1:8000/admin/`
   for the admin panel.

## Pushing this project to GitHub

1. Create a new, empty repository on GitHub (don't initialize it with a
   README/.gitignore — you already have those here). Copy its URL, e.g.
   `https://github.com/YOUR_USERNAME/YOUR_REPO.git`.

2. From inside this project folder, run:

   ```bash
   git init
   git add .
   git commit -m "Initial commit: Django blog app"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

   If prompted for credentials, GitHub no longer accepts your account
   password over HTTPS — use a
   [personal access token](https://github.com/settings/tokens) instead, or
   push via SSH if you have an SSH key set up with GitHub.

3. Refresh the GitHub repo page — your code should now be there.

## Notes for production

Before deploying anywhere public:
- Set `DJANGO_SECRET_KEY` to a strong random value via an environment variable.
- Set `DJANGO_DEBUG=False`.
- Set `DJANGO_ALLOWED_HOSTS` to your real domain(s).
- Switch from SQLite to Postgres/MySQL for anything beyond light personal use.
- Serve static files properly (e.g. WhiteNoise or a CDN) instead of Django's dev server.

## License
MIT License
