
## Project set up guide
### Clone the repo
    git clone https://github.com/yourusername/travel_agency.git
    cd travel_agency
### Create virtual environment
    python3 -m venv venv
### Activate the environment
    Windows : env\Scripts\activate
    Linux: source venv/bin/activate
### Install python libraries
    pip install -r requirements.txt
### Install node libraries (tailwind etc)
    python3 ./manage.py tailwind install
### Set up database
    sudo -u postgres psql (opening postgre shell)
    create database travel_db;
    create user admin with password '1234';
    alter role admin set client_encoding to 'utf8';
    alter role admin set default_transaction_isolation to 'read committed';
    alter role admin set timezone to 'utc';
    grant all privileges on database travel_db to admin;
    grant all on schema public to admin;

    python manage.py migrate
    python manage.py createsuperuser
    
### Done!!!