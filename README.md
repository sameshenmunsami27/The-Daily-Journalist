# The-Daily-Journalist
This is a news application for general news

The Daily Journalist

##  Project Overview
**The Daily Journalist** is a Django-powered news platform designed for managing general news articles and newsletters. It features a robust, role-based permission system and a centralized template architecture to ensure a clean and maintainable codebase.

### Main Features
* **Article Management:** Full content lifecycle for news stories.
* **Newsletter Feed:** Specialized views for periodic newsletters.
* **Permissions Engine:** Custom access levels for Readers, Editors, and Journalists.
* **MySQL Persistence:** Reliable data storage for all user and news data.

---

##  User Roles & Permissions
Access control is managed via the Django Admin panel using three distinct groups:

| Role | Permissions |
| :--- | :--- |
| **Reader** | Can only view articles and newsletters and subscribe to pulishers and authors. |
| **Editor** | Can view, update, and delete articles and newsletters. |
| **Journalist** | Can create, view, update, and delete articles and newsletters. |



---

##  Dependencies
The project requires the following environment to run correctly:
* **Python 3.x**
* **Django 6.0.2** (Web Framework)
* **mysqlclient 2.2.8** (MySQL Database Connector)
* **Pillow 12.1.1** (Image Processing for Article Media)
* **sqlparse & asgiref** (Django Internals)

---

##  Installation & Setup Instructions
1. Initialize Virtual Environment
Navigate to the project root and create a localized Python environment to keep your project dependencies isolated:

PowerShell
python -m venv .venv
.\.venv\Scripts\activate
2. Install Required Packages
You can install all dependencies at once using the requirements file, or run the manual command provided below.

Option A (Recommended):

PowerShell
pip install -r requirements.txt

Option B (Manual):

PowerShell
pip install django djangorestframework mysqlclient Pillow
Note: djangorestframework is required for the API features of "The Daily Journalist," and Pillow is required for processing article images.

3. Database Setup
Before running the application, ensure your data layer is ready:

Open your MySQL Control Panel (XAMPP or MySQL Workbench).

Start the MySQL service.

Ensure your settings.py is configured for your local MySQL instance (Default: no password).

4. Running the Project
Step A: Database Migrations
Sync your Django models with the MySQL database schemas:

PowerShell
python manage.py makemigrations
python manage.py migrate
Step B: Launch Development Server
PowerShell
python manage.py runserver
Access the application at: http://127.0.0.1:8000/

 Usage Instructions
Administrative Setup: Access /admin to create your Superuser.

Group Assignment: Manually create groups named Reader, Editor, and Journalist. Assign users to these groups to trigger the built-in site permissions.

Content Creation: Log in with a Journalist account to begin drafting and submitting new articles.

 Additional Notes
Template Architecture: All HTML files are located in the root /templates/ folder. Do not create subdirectories within templates (e.g., no /templates/news/), as the project is configured for a flat structure.

Environment: Always ensure the .venv is activated before running any management commands. If you see ModuleNotFoundError, double-check that (.venv) appears in your terminal prompt.
