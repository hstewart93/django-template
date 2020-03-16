# django-template
Template django repository with database connection for testing out OOP and database relations.
This is a Python 3 project running Django 3. Clone down this repo and follow the installation instructions
to get started with a Django project.

## Installation

### Pipenv
This project uses pipenv to manage python package requirements. This means that all development should be done
within the virtual environment. The following command will initialise the virtual environment and install the
dependencies, which can be managed in the `Pipfile`.

```bash
pipenv install --dev
```

We use the `--dev` flag to hierarchically install the development and production environments. This means,
if you have development requirements such as pytest these will be installed, if you just run `pipenv install`
you development requirements will not.

To activate your virtual environment, run:

```bash
pipenv shell
```

To add a new requirement to your virtual environment 'template', add a new line to the Pipfile
with a pinned version. Alternatively, run the following for a production requirement:

```bash
pipenv install my-library
```

Or for a development requirement:

```bash
pipenv install --dev my-dev-library
```

If you want to find the location of your virtual environment, eg. for setting up your IDE run the
following from within the shell.

```bash
pipenv --venv
```

### Pre-commit
This project uses the `black` auto formatter which can be run on `git commit` if you install pre-commit.
Black formats the code committed to a pre-defined standard which can be customised to your needs if required.
See the [docs](https://black.readthedocs.io/en/stable/) for the defined code style.

Pre-commit is also configured to run `flake8` on commit which will pick up linting errors. See the [docs](https://pypi.org/project/flake8/).

To install pre-commit run the following from *within* your virtual environment.

```bash
pre-commit install
```

Black and flake8 should now run on commit. If there are formatting errors the commit will fail and you will
need to re-commit the changes made by black.

### Database
You will need to create the database for the application to connect to. The Django project uses `postgres` which
you will need to have installed on your machine. To create the database run the following:

```bash
createdb django_db
```

To migrate any Django relations generated on setup and any existing model relations in your code you will need to run

```bash
python manage.py migrate
```

Once you have some models in your code you will want to create a migration to run against your database.
Do this by running

```bash
python manage.py makemigrations
```

Run these migrations using the `python manage.py migrate` command as above. See the Django [docs](https://docs.djangoproject.com/en/3.0/)
for all further instructions on setup and development.
