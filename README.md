# travel_agency_web
Here is a clean, professional README.md file tailored to your specific stack.

You can create a file named README.md in your project root and paste this content in.

✈️ Travel Agency Portal (Django Monolith)

This project uses the "Modern Monolith" stack:

Backend: Django + Wagtail CMS

Database: PostgreSQL

Frontend Styling: Tailwind CSS + DaisyUI

Interactivity: HTMX + Alpine.js

🛠 Prerequisites

Before starting, ensure you have these installed on your machine:

Python 3.10+

Node.js & npm (Required for Tailwind CSS compilation)

PostgreSQL

🚀 Getting Started (First Time Setup)

Follow these steps to set up the project locally after cloning the repo.

1. Database Setup

Create a local PostgreSQL database named travel_db.

code
SQL
download
content_copy
expand_less
-- Run this in psql or pgAdmin
CREATE DATABASE travel_db;

Note: Check backend/settings/base.py if you need to adjust the database user/password (Default: postgres/password).

2. Virtual Environment

Do not skip this. You need an isolated environment for Python packages.

code
Bash
download
content_copy
expand_less
# Windows
python -m venv venv
venv\Scripts\activate

# Mac / Linux
python3 -m venv venv
source venv/bin/activate
3. Install Python Dependencies
code
Bash
download
content_copy
expand_less
pip install -r requirements.txt
4. Install Frontend Dependencies (Tailwind)

We use django-tailwind. You need to install the Node packages.

code
Bash
download
content_copy
expand_less
python manage.py tailwind install
5. Setup Database Schema
code
Bash
download
content_copy
expand_less
python manage.py migrate
6. Create Admin User

Create your login for the Wagtail CMS / Django Admin.

code
Bash
download
content_copy
expand_less
python manage.py createsuperuser
🏃‍♂️ How to Run the Project

Because we are using Tailwind CSS, you need two terminal windows running simultaneously.

Terminal 1: The Django Server

Runs the actual website logic.

code
Bash
download
content_copy
expand_less
# Make sure venv is active!
python manage.py runserver
Terminal 2: The Tailwind Watcher

Watches your HTML files and automatically recompiles the CSS when you save.

code
Bash
download
content_copy
expand_less
# Make sure venv is active!
python manage.py tailwind start
Access the Site

Public Site: http://127.0.0.1:8000

CMS Admin: http://127.0.0.1:8000/admin

📦 Workflow for Adding Packages

Since we are collaborating, follow this rule when installing new libraries.

If you install a Python Package (e.g. Stripe):

pip install stripe

Update the file: pip freeze > requirements.txt

Commit and Push requirements.txt.

If you pull code and it crashes:

It probably means the other person added a library.

Run: pip install -r requirements.txt

Run: python manage.py migrate (in case models changed)

📁 Project Structure

backend/ - Main Django project settings.

home/ - The homepage app (Wagtail).

theme/ - Contains Tailwind CSS configuration.

search/ - Wagtail search functionality.

manage.py - Django task runner.