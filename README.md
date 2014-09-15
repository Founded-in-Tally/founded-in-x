# Founded In Romania

### Install the Python packages manager
```shell
sudo apt-get install python-pip
```
### Install the virtualenv Python package
```shell
sudo apt-get install python-virtualenv
```
### Install virtualenv itself
```shell
sudo pip install virtualenv
```
### Create virtualenv
```shell
cd founded-in-romania
virtualenv venv
```
### Activate virtualenv
```shell
source venv/bin/activate
```
### Install all necessary packages
```shell
pip install -r requirements.txt
```

### Tested
```shell
python run.py
```
Go to http://localhost:5000/