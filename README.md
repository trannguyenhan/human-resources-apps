## Install
### Step 1: Clone project
```
git clone https://github.com/trannguyenhan/human-resources-apps.git
```

### Step 2: Check python version
Odoo requires Python 3.7 or later, check your python: 
```
python3 --version
pip3 --version
```

### Step 3: Install package
Checkout path to project and install package: 
```
pip3 install setuptools wheel
pip3 install -r requirements.txt
```

If you encounter errors about `error: command 'x86_64-linux-gnu-gcc' failed with exit status 1` will install package: 
```
sudo apt-get install python3-dev
sudo apt-get install python-dev
sudo apt-get install libpq-dev python-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev libffi-dev
```

If you encounter errors about: 
```
ERROR: jinja2 3.0.2 has requirement MarkupSafe>=2.0, but you'll have markupsafe 1.1.0 which is incompatible
ERROR: flask 2.0.1 has requirement Jinja2>=3.0, but you'll have jinja2 2.11.2 which is incompatible.
RROR: flask 2.0.1 has requirement Jinja2>=3.0, but you'll have jinja2 2.11.2 which is incompatible.
ERROR: flask 2.0.1 has requirement Werkzeug>=2.0, but you'll have werkzeug 0.16.1 which is incompatible
```

modify version in file requirements.txt

### Step 4: Install postgre SQL
Install postgre in link: [https://www.postgresql.org/download/](https://www.postgresql.org/download/)

### Step 5: Create account 
Account default is postgre but Odoo forbids connecting as postgre, so you must create new account and database with name same with your username:
```
sudo -u postgres createuser trannguyenhan
sudo -u postgres createdb -O trannguyenhan trannguyenhan
```
- with command 2 trannguyenhan parameter first is username and trannguyenhan parameter second is database

### Step 6: Run
```
python3 ./odoo-bin -i base -d trannguyenhan
```

references: [https://www.odoo.com/documentation/15.0/administration/install/install.html#source-install](https://www.odoo.com/documentation/15.0/administration/install/install.html#source-install)