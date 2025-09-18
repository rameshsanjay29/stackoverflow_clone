# StackOverflowClone (Flask)

Features implemented:
- Authentication (signup/login, OTP/email verification stubs)
- Forgot-password with 1-per-day rule and random password generator (no digits/special chars)
- Public space (posting limits based on friends)
- Reward system with points ledger and transfer rules
- Multi-language switch with OTP rules (French -> email OTP; others -> phone OTP)
- Login history recording (browser, OS, device, IP)
Let’s set up and run your StackOverflow Clone project step by step.

1. Prerequisites
   Make sure you have installed:
   Python 3.9+
   pip (Python package manager)
   virtualenv (optional but recommended)
   SQLite (already included with Python)

2. Extract the Project

   Unzip the file you downloaded:
   unzip stackoverflow_clone.zip
   cd stackoverflow_clone

3. Create a Virtual Environment
   python -m venv venv
   source venv/bin/activate     # On Linux/Mac
   venv\Scripts\activate        # On Windows

4. Install Dependencies
   pip install -r requirements.txt

5. Configure Environment Variables

   Copy .env.sample to .env and update values:
   cp .env.sample .env
   Open .env and change:

SECRET_KEY=your_secret_key
DATABASE_URL=sqlite:///app.db
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=your_email@gmail.com
MAIL_PASSWORD=your_app_password   # Use app password, not Gmail login

6. Initialize Database
Run:
 flask db init
 flask db migrate -m "Initial migration"
 flask db upgrade
 This creates the app.db SQLite database.

7. Run the App
 flask run
 Or using python:
 python run.py

8. Testing Features

  Signup/Login → /auth/signup & /auth/login (send JSON with email/password)
  Forgot Password → /auth/forgot (once per day)
  Post in Public Space → /public/post
  Transfer Points → /points/transfer
  Web pages → check /, /public
 
