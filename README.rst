Tangelo Default Site/Container
==============================

Not a whole lot here - a basic Django/Bootstrap site made with CookieCutter, intended as an example container site for
devs getting started with the [Tangerine](https://github.com/shacker/tangerine) blog engine.

This project uses the new pipenv system in place of the old pip + virtualenv

Tangelo uses the new [pipenv](https://docs.pipenv.org/) system, which combines virtual environment and dependency
management into a unified tool. In other words, the single `pipenv` command replaces all of the virtual environment
*and* `pip` commands you may be accustomed to. `pipenv` is the new *officially recommended* system for venv and
packagement management in python.

.. image:: https://img.shields.io/badge/built%20with-Cookiecutter%20Django-ff69b4.svg
     :target: https://github.com/pydanny/cookiecutter-django/
     :alt: Built with Cookiecutter Django

:License: MIT


Installation
------------

```
pip3 install --user git+https://github.com/kennethreitz/pipenv.git
createdb tangelo
cd ~/dev  # Or whatever your dev dir is
git clone git@github.com:shacker/tangelo.git
cd tangelo
pipenv --python 3.6   # Initializes the virtual environment
pipenv install --dev  # Installs all dependencies
pipenv shell  # Activates the environment
./manage.py migrate
```

Setting Up Users
----------------

* To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you'll see a "Verify Your E-mail Address" page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user's email should be verified and ready to go.

* To create an **superuser account**, use this command::

    $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

Test coverage
-------------

To run the tests, check your test coverage, and generate an HTML coverage report::

    $ pytest
    $ coverage html
    $ open htmlcov/index.html
