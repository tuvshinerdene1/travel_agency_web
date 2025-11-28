
## Project set up guide
### Clone the repo
    git clone https://github.com/yourusername/travel_agency.git
    cd travel_agency
### Create virtual environment
    python -m venv venv
### Activate the environment
    Windows : env\Scripts\activate
    Linux: source venv/bin/activate
### Install python libraries
    pip install -r requirements.txt
### Install node libraries (tailwind etc)
    npm install
### Set up database (create own postgre db, see the backend/setting/base.py)
    python manage.py migrate
    python manage.py createsuperuser
    (sudo -u postgres psql ) -- for opening postgre shell
