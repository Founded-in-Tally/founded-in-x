# Founded In Tally

  * Website to be used for [Founded in Tally](http://foundedintally.com), originally forked from [www.foundedx.com](http://foundedx.com).

## Features
  1. Shows the first page with the list of startups.
  2. Shows an about page for the origin country of the startups.
  3. Has a backoffice to ease the management of the database.
  4. Register new companies with a Typeform form

## Technologies

### Server-side

  * [Flask](http://flask.pocoo.org/): web microframework for Python based on Werkzeug and Jinja 2.
  * [FlaskAdmin](https://flask-admin.readthedocs.io/en/latest/): Flask extension for building an admin interface on top of an existing data model.
  * [PostgreSQL](http://www.postgresql.com): Relational database, used to store the company descriptions, user accounts for backoffice and key-value pairs.

### Client-side
  * [jQuery](http://www.jquery.com): Cross-browser compliant JavaScript code.
  * [Modernizr](http://modernizr.com/): JavaScript library that detects HTML5 and CSS3 features in the browser.
  * [Font Awesome](http://fortawesome.github.io/Font-Awesome/): iconic font and CSS toolkit.

## Installation Instructions

### Quick Overview

1. Install and configure PostgreSQL
1. Install VirtualEnv/VirtualEnvWrapper, create virtual env, and install requirements
1. Configure app
  * Export `APP_SETTINGS` and `DATABASE_URL`
      * e.g., `export APP_SETTINGS="config.DevelopmentConfig"`
      * e.g., `export DATABASE_URL="postgresql://myuser:password@localhost/mydb"`
  * Additional configuration, including admin user/password in `config.py`)
      * Ensure `config.py` is added to `.gitignore`
1. Run `python run.py --setup` to set up the database and create the admin user
1. Run `python run.py` to run the app server
1. Go to [http://localhost:5000](http://localhost:5000) for the front-end and [http://localhost:5000/admin](http://localhost:5000/admin) for the administrator interface


### MacOS Installation

#### Install and configure PostgreSQL
1. Install and start PostgreSQL (alternatively, [pgAdmin](https://www.pgadmin.org/) is a great utility)
```
$ brew install postgresql
$ brew services start postgresql
```

2. Create the database/user, for example,
```
$ psql
#= create database founded_in_tally;
#= create user tally_user;
#= alter user tally_user with encrypted password "tally_password";
#= grant all privileges on database founded_in_tally to tally_user;
```

3. Set environment variable with database connection info
```
$ export DATABASE_URL="postgresql://tally_user:tally_password@localhost/founded_in_tally"
```

#### Install the Python package manager

Pip (package manager for Python) comes included with certain versions of Python, but if you find that your system is missing it, follow the installation instructions [here](https://pip.pypa.io/en/stable/installing/).

#### Work in a Python virtualenv

1. Install [VirtualEnv](https://virtualenv.pypa.io/en/stable/)/[VirtualEnvWrapper](https://virtualenvwrapper.readthedocs.io/en/latest/) and [configure VirtualEnvWrapper](https://virtualenvwrapper.readthedocs.io/en/latest/install.html#shell-startup-file)

2. Create and activate virtual env
```
$ mkvirtualenv founded_in_tally
$ workon founded_in_tally
```

3. Install requirements for project
```
$ pip install -r requirements.txt
```

### Linux / Ubuntu Installation

#### Install and configure PostgreSQL
  1. Install PostgreSQL
    ```
    sudo apt-get install postgresql postgresql-contrib pgadmin3
    ```

  2. Create a database user with full rights on it
    ```
    sudo -u postgres createuser -D -A -P myuser
    sudo -u postgres createdb -O myuser mydb
    ```

  3. Restart the PostgreSQL server
    ```
    sudo /etc/init.d/postgresql restart
    ```

#### Install the Python package manager
  ```
  sudo apt-get install python-pip
  ```

#### Work in a Python virtualenv
  1. Install virtualenv
    ```
    sudo pip install virtualenv
    ```

  2. After cloning the repo create the virtualenv
    ```
    cd founded-in-tally
    virtualenv venv
    ```

  3. Add the following lines to venv/bin/activate file
    ```
    export DATABASE_URL="postgresql://myuser:password@localhost/mydb"
    export APP_SETTINGS="config.DevelopmentConfig"
    ```

  4. Activate virtualenv
    ```
    source venv/bin/activate
    ```

  5. Install all necessary packages
    ```
    pip install -r requirements.txt
    ```

## License

This software is licensed under the MIT License. See [LICENSE file](https://github.com/Founded-in-Tally/founded-in-tally/blob/master/LICENSE.md) for details.

Portions of this software are copyright of their own owners as described in the files containing them.

## TODO

- Models
- Form to submit company (startup)
- Form to submit contributor
- Form to submit events
- Load and display companies on index
- Load and display contributors on contributors page
- Load and display events on events page
- Navigation updates (add new pages)
- CONTENT/COPY to pages
- Deploy to Heroku
- (Admin user creation)
- Companies input (admin)
