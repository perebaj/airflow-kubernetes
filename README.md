# airflow-kubernetes

Trying to understand how Kubernetes applications are deployed, learning on my personal environment.
On this project, I learned how helm take care about dependencies and how to use Artifact Hub to build and deploy easily an open source application like Airflow.
Also, how create a custom Airflow image to install Python packages and sync all using an GitHub repository.
I have intent to use continuous integration on this repository, simulating a production environment where app and packages versions has to updated, all of that to teams that not necessary have DevOps or infra skills can work together.

```bash

minikube start

kubeclt create namespace airflow

kubens (<--- you have to select airflow namespace)

eval minikube docker-env

docker build -t airflow-custom:1.0.0

helm install airflow apache-airflow/airflow -f ./airflow-kubernetes-setup/values.yaml --namespace airflow

minikube dashboard

kubectl port-forward svc/airflow-webserver 8080:8080 --namespace airflow
```