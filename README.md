# Placement Portal Application

A Flask-based campus placement management portal for students, companies, and placement administrators. The application uses SQLite for persistence, SQLAlchemy for data access, and server-rendered Jinja templates with Bootstrap-compatible styling.

## Features

- Student registration, profile management, and placement-drive discovery
- Company registration, profile management, and drive creation
- Student applications, shortlisting, and application-status tracking
- Administrator dashboard for approval, moderation, and blacklist workflows
- Search and profile views for students and companies
- SQLite database created automatically on first startup

## Technology Stack

- Python 3.10+
- Flask
- Flask-SQLAlchemy and SQLAlchemy
- SQLite
- Jinja2 templates
- HTML/CSS with Bootstrap-compatible markup

## Project Structure

```text
.
├── app.py                  # Flask application entry point
├── application/
│   ├── controllers.py      # Routes and request handling
│   ├── database.py         # SQLAlchemy configuration
│   └── models.py           # User, company, drive, and application models
├── templates/              # Jinja pages for each user workflow
├── static/                 # Stylesheets and static assets
├── instance/               # Local SQLite database files
└── requirements.txt        # Python dependencies
```

## Run Locally

```bash
git clone https://github.com/23f1000318/Placement_Portal_Application.git
cd Placement_Portal_Application

python -m venv .venv
source .venv/bin/activate       # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

Open `http://127.0.0.1:5000` in a browser.

On first startup, the application creates the database and a development administrator account if one does not already exist:

```text
Username: admin
Password: admin123
```

Change or remove these development credentials before using the application in a real deployment.

## Database

The default configuration uses SQLite. The database is initialized automatically by `create_app()` and is stored in the Flask instance directory. For production use, move credentials and database configuration to environment variables and disable Flask debug mode.

## Deployment

This repository does not currently include a production deployment configuration. A deployment needs a Python-compatible host, a production WSGI server such as Gunicorn, persistent storage for SQLite or an external database, and secure administrator credentials.

## License

See [LICENSE](LICENSE) for license information.
