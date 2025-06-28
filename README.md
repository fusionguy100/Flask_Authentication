# Flask Authentication

A minimal Flask application showcasing secure user authentication flows, including registration, login/logout, protected content, and file downloads. Users are stored in a SQLite database with passwords hashed using Werkzeug, and session management is handled by Flask-Login.

---

## Features

- **User Registration**: New users can create accounts with unique emails and securely hashed passwords (Werkzeug).
- **User Login / Logout**: Authenticate via Flask-Login; sessions are maintained securely.
- **Protected Routes**: Access-controlled pages (e.g., `/secrets`) that require login.
- **File Download Protection**: A secure endpoint for downloading a protected resource (`/download`) available only to authenticated users.
- **Database Integration**: User data persisted in SQLite via SQLAlchemy ORM.
- **Flask Best Practices**: Utilizes Flask's application factory pattern, `flask_wtf` for form handling with CSRF protection, and environment-based configuration for sensitive settings.

---

## Getting Started

### Prerequisites

- Python 3.7+
- `virtualenv` or `venv` for creating an isolated environment

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/fusionguy100/Flask_Authentication.git
   cd Flask_Authentication
   ```

2. **Create and activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate    # on macOS/Linux
   venv\Scripts\activate     # on Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set environment variables**

   Create a `.env` file in the project root and add:

   ```ini
   SECRET_KEY=your_secret_key_here
   ```

5. **Initialize the database**

   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```

6. **Run the application**

   ```bash
   flask run
   ```

   By default, the app runs at `http://127.0.0.1:5000/`.

---

## Project Structure

```
Flask_Authentication/
├── app.py            # Application entry point and route definitions
├── models.py         # SQLAlchemy User model
├── forms.py          # WTForms definitions for registration and login
├── templates/        # Jinja2 templates (register.html, login.html, secret.html, index.html)
├── static/           # Static files (CSS, JS)
├── requirements.txt  # Python dependencies
└── README.md         # Project documentation
```

---

## Usage

1. **Register a new user** at `/register`.
2. **Log in** at `/login`.
3. Visit the **protected page** `/secrets` or download the protected file at `/download`.
4. **Log out** at `/logout`.

---

## Contributing

Contributions are welcome! Please:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/my-feature`).
3. Commit your changes (`git commit -am 'Add my feature'`).
4. Push to the branch (`git push origin feature/my-feature`).
5. Open a Pull Request.
