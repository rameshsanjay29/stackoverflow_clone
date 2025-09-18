# StackOverflowClone (Flask)

A simple StackOverflow-like app built with Flask.

## Features

* Authentication (signup/login, OTP/email stubs)
* Forgot-password (1 per day, random letters-only password)
* Public space (posting limits based on friends)
* Reward system (points ledger + transfer rules)
* Multi-language OTP (French → email, others → phone)
* Login history (browser, OS, device, IP)

## Setup & Run

1. **Prerequisites**

   * Python 3.9+
   * pip
   * virtualenv (optional)
   * SQLite (included)

2. **Extract project**

   ```bash
   unzip stackoverflow_clone.zip
   cd stackoverflow_clone
   ```

3. **Virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\\Scripts\\activate
   ```

4. **Install deps**

   ```bash
   pip install -r requirements.txt
   ```

5. **Config env**

   ```bash
   cp .env.sample .env
   ```

   Edit `.env`:

   ```env
   SECRET_KEY=your_secret_key
   DATABASE_URL=sqlite:///app.db
   MAIL_SERVER=smtp.gmail.com
   MAIL_PORT=587
   MAIL_USERNAME=your_email@gmail.com
   MAIL_PASSWORD=your_app_password
   ```

6. **Init DB**

   ```bash
   flask db init
   flask db migrate -m "Initial migration"
   flask db upgrade
   ```

7. **Run app**

   ```bash
   flask run
   # or
   python run.py
   ```

## Test Features

* Signup/Login → `/auth/signup`, `/auth/login`
* Forgot Password → `/auth/forgot`
* Post in Public → `/public/post`
* Transfer Points → `/points/transfer`
* Web pages → `/`, `/public`
