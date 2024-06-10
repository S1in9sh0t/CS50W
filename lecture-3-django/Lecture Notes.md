# Lecture Notes

DJANGO

`echo 'export PATH="/opt/homebrew/bin/django-admin:$PATH"' >> ~/.zshrc`

`source ~/.zshrc`

https://code.visualstudio.com/docs/python/tutorial-django

## Breakdown

Create a project environment for the Django tutorial

In this section, you create a virtual environment in which Django is installed. Using a virtual environment avoids installing Django into a global Python environment and gives you exact control over the libraries used in an application. A virtual environment also makes it easy to Create a requirements.txt file for the environment.

On your file system, create a project folder for this tutorial, such as hello_django.

In that folder, use the following command (as appropriate to your computer) to create a virtual environment named .venv based on your current interpreter:

# Linux
sudo apt-get install python3-venv    # If needed
python3 -m venv .venv
source .venv/bin/activate

# macOS
python3 -m venv .venv
source .venv/bin/activate

Open the project folder in VS Code by running code ., or by running VS Code and using the File > Open Folder command.

In VS Code, open the Command Palette (View > Command Palette or (⇧⌘P)). Then select the Python: Select Interpreter command:

Django tutorial: opening the Command Palette in VS Code

The command presents a list of available interpreters that VS Code can locate automatically (your list will vary; if you don't see the desired interpreter, see Configuring Python environments). From the list, select the virtual environment in your project folder that starts with ./.venv or .\.venv:

Django tutorial: Selecting the virtual environment for Python

Run Terminal: Create New Terminal (⌃⇧`) from the Command Palette, which creates a terminal and automatically activates the virtual environment by running its activation script.

The selected environment appears on the right side of the VS Code status bar, and notices the ('.venv': venv) indicator that tells you that you're using a virtual environment:

Django tutorial: selected environment showing in the VS Code status bar

Update pip in the virtual environment by running the following command in the VS Code Terminal:

python -m pip install --upgrade pip
Install Django in the virtual environment by running the following command in the VS Code Terminal:

python -m pip install django
You now have a self-contained environment ready for writing Django code. VS Code activates the environment automatically when you use Terminal: Create New Terminal (⌃⇧`). If you open a separate command prompt or terminal, activate the environment by running source .venv/bin/activate (Linux/macOS) or .venv\Scripts\Activate.ps1 (Windows). You know the environment is activated when the command prompt shows (.venv) at the beginning.

Create and run a minimal Django app
In Django terminology, a "Django project" is composed of several site-level configuration files, along with one or more "apps" that you deploy to a web host to create a full web application. A Django project can contain multiple apps, each of which typically has an independent function in the project, and the same app can be in multiple Django projects. An app, for its part, is just a Python package that follows certain conventions that Django expects.

To create a minimal Django app, then, it's necessary to first create the Django project to serve as the container for the app, then create the app itself. For both purposes, you use the Django administrative utility, django-admin, which is installed when you install the Django package.

Create the Django project
In the VS Code Terminal where your virtual environment is activated, run the following command:

django-admin startproject web_project .
This startproject command assumes (by use of . at the end) that the current folder is your project folder, and creates the following within it:

manage.py: The Django command-line administrative utility for the project. You run administrative commands for the project using python manage.py <command> [options].

A subfolder named web_project, which contains the following files:

__init__.py: an empty file that tells Python that this folder is a Python package.
asgi.py: an entry point for ASGI-compatible web servers to serve your project. You typically leave this file as-is as it provides the hooks for production web servers.
settings.py: contains settings for Django project, which you modify in the course of developing a web app.
urls.py: contains a table of contents for the Django project, which you also modify in the course of development.
wsgi.py: an entry point for WSGI-compatible web servers to serve your project. You typically leave this file as-is as it provides the hooks for production web servers.
Create an empty development database by running the following command:

python manage.py migrate
When you run the server the first time, it creates a default SQLite database in the file db.sqlite3 that is intended for development purposes, but can be used in production for low-volume web apps. For additional information about databases, see the Types of databases section.

To verify the Django project, make sure your virtual environment is activated, then start Django's development server using the command python manage.py runserver. The server runs on the default port 8000, and you see output like the following output in the terminal window:

Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
June 13, 2023 - 18:38:07
Django version 4.2.2, using settings 'web_project.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
Django's built-in web server is intended only for local development purposes. When you deploy to a web host, however, Django uses the host's web server instead. The wsgi.py and asgi.py modules in the Django project take care of hooking into the production servers.

If you want to use a different port than the default 8000, specify the port number on the command line, such as python manage.py runserver 5000.

Ctrl+click the http://127.0.0.1:8000/ URL in the terminal output window to open your default browser to that address. If Django is installed correctly and the project is valid, you see the default page shown below. The VS Code terminal output window also shows the server log.

Django tutorial: default view of empty Django project

When you're done, close the browser window and stop the server in VS Code using Ctrl+C as indicated in the terminal output window.

