# airflow-kubernetes



```bash

minikube start

kubeclt create namespace airflow

eval minikube docker-env

docker build -t airflow-custom:1.0.0

helm install airflow apache-airflow/airflow -f ./airflow-kubernetes-setup/values.yaml --namespace airflow

minikube dashboard

kubectl port-forward svc/airflow-webserver 8080:8080 --namespace airflow
```