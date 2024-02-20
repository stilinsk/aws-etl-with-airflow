# aws-etl--airflow
### we will be using linux commands so if you are using windows as your operating systm take time to understand how these commands work and when used to understand fully our work flow
These are the commands to connecting the airflow instance to an ec2 instance
```
sudo apt update

sudo apt install python3-pip

sudo apt install sqlite3

sudo apt install python3.10-venv

python3 -m venv  venv

sudo apt-get install libpq-dev

source venv/bin/activate

pip install "apache-airflow[postgres]==2.5.0" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.5.0/constraints-3.7.txt"

airflow db init

sudo apt-get install postgresql postgresql-contrib

sudo -i -u postgres

psql

CREATE DATABASE airflow;
CREATE USER airflow WITH PASSWORD 'airflow';
GRANT ALL PRIVILEGES ON DATABASE airflow TO airflow;

sed -i 's#sqlite:////home/ubuntu/airflow/airflow.db#postgresql+psycopg2://airflow:airflow@localhost/airflow#g' airflow.cfg

sed -i 's#SequentialExecutor#LocalExecutor#g' airflow.cfg

pip install apache-airflow-providers-amazon

sudo apt install awscli

aws configure

# Enter your AWS access key, secret key, region, and preferred output format

airflow db init

airflow users create -u airflow -f airflow -l airflow -r Admin -e airflow@gmail.com

airflow webserver &

Remember we will be using the sudo nano command to acces the file into our airflow instance then we will be using to code and save the  pyton script above.Remeber the python script  must be saved in the airflow instance for it to work 

airflow scheduler

airlow standalone
```
