# airflow-kubernetes



```bash

minikube start

kubeclt create namespace airflow

helm install airflow bitnami/airflow -f ./airflow-kubernetes-setup/values.yaml --namespace airflow

minikube dashboard

kubeclt port-forward --namespace airflow svc/airflow 8080:8080
```