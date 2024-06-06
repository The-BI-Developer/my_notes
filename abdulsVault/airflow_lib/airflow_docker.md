1. docker version

docker --version
docker-compose --version #requires separate installation

2. docker recipe

curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.4.1/docker-compose.yaml' #this is for 2.4.1

3. folder structure

./dags ./logs ./plugins
touch .env #will be used by docker

4. configuring env vars

echo -e "AIRFLOW_UID=$(id -u)" > .env

AIRFLOW_UID=50000 #for windows add this line to suppress image start msg


5. disable sample dags

#./docker-compose.yaml
environment:
    &airflow-common-env
    AIRFLOW__CORE__EXECUTOR: CeleryExecutor
    AIRFLOW__DATABASE__SQL_ALCHEMY_CONN: postgresql+psycopg2://airflow:airflow@postgres/airflow
    # For backward compatibility, with Airflow <2.3
    AIRFLOW__CORE__SQL_ALCHEMY_CONN: postgresql+psycopg2://airflow:airflow@postgres/airflow
    AIRFLOW__CELERY__RESULT_BACKEND: db+postgresql://airflow:airflow@postgres/airflow
    AIRFLOW__CELERY__BROKER_URL: redis://:@redis:6379/0
    AIRFLOW__CORE__FERNET_KEY: ''
    AIRFLOW__CORE__DAGS_ARE_PAUSED_AT_CREATION: 'true'
    AIRFLOW__CORE__LOAD_EXAMPLES: 'false' #disabled dag examples
    AIRFLOW__API__AUTH_BACKENDS: 'airflow.api.auth.backend.basic_auth'
    _PIP_ADDITIONAL_REQUIREMENTS: ${_PIP_ADDITIONAL_REQUIREMENTS:-}


6. docker installs airflow

docker-compose up airflow-init

docker ps #check daemon active

#in ui - green at bottom left means daemon active

7. future runs

docker-compose up

8. web app

http://localhost:8080/home #airflow/airflow [credentials]

9. execute airflow dag

from datetime import datetime

from airflow import DAG
from airflow.decorators import task

with DAG(
    dag_id="demo_dag",
    start_date=datetime(2022, 1, 1),
    schedule="0 0 * * *"
    ) as dag:

    @task()
    def test_airflow():
        print("Executed using Apache Airflow ✨")

    test_airflow()

docker-compose run airflow-worker airflow info #docker manages everything, access  airflow-worker containing running instance
