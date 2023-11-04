# python-template

https://armandsauzay.medium.com/python-project-setup-a-step-by-step-guide-to-industry-best-practices-dbce717b2d12

Template for python-based repositories.

## Usage

### Virtual environments

1. Install virtualenv. You can install virtualenv using pip, the Python package manager. Open your terminal and run:

> pip install virtualenv.

2. Create a virtual environment. Navigate to your project directory and run:

> virtualenv venv

This will create a new virtual environment in the current directory called venv.

3. Activate the virtual environment. To activate the virtual environment, run:

> source venv/bin/activate (Linux/Mac)

or

> venv\Scripts\activate (Windows)

When you’re done working on your project, you can deactivate the virtual environment by running deactivate in your terminal.

### Poetry

I use Poetry to manage virtual environments for all of my Python projects. Here’s how to use Poetry:

1. Install Poetry. You can install Poetry by following the installation instructions on the Poetry website.

2. Create a new project. Navigate to the directory where you want to create your project and run:

> poetry new myproject

 This will create a new project directory called myproject with a basic project structure inside.

3. Activate the virtual environment. To activate the virtual environment for your project, run:

> poetry shell

 This will create a new virtual environment and activate it. If you want to run a command in the virtual environment without activating it, use poetry run <command> like this: poetry run python main.py

4. Install packages and dependencies. To install packages and dependencies for your project, run:

> poetry add package_name

 This will install the package and add it to your project's pyproject.toml file. More on this later.

Once you’ve installed your packages and dependencies, you can deactivate the virtual environment by running exit in your terminal.

poetry saves all of your dependencies to pyproject.toml and pins them to a specific version in a poetry.lock file. This ensures you can replicate your project exactly across different environments.

### Test

The de facto standard for robust testing in Python is Pytest. Pytest comes with powerful features out of the box like detailed test failure output and a simple API. It also integrates with Django, Jupyter, and dozens more Python tools.

# add pytest to your test dependencies if it is not already there 
> poetry add --group test pytest

# run test using pytest
> poetry run pytest

### Code Formatting

Code formatting refers to the way that code is structured and styled, including things like indentation, line spacing, and naming conventions. It’s about making sure that the code is easy to read and understand, which can make it easier to debug and maintain over time.

> poetry add black --group dev

### Code Linting

code linting involves analyzing the code for potential errors or issues that could cause problems. Linters look at things like syntax errors, unused variables, and other potential bugs, and can provide suggestions for how to fix them.

> poetry add pylint --group dev


# install flake8, black, isort and mypy, add them to lint dependencies
> poetry add --group lint flake8 black isort mypy

A few examples of linting your code include:

# Lint using mypy:
> poetry run mypy hello_world_cli/cli.py

# Lint using flake8
poetry run flake8 hello_world_cli/cli.py

# Lint using black 
poetry run black hello_world_cli/cli.py