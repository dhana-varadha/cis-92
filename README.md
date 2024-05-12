# My CIS-92 Project 

This repository has the starter code for CIS-92. 

By Dhana Varadha

# Description of the variables in config.yaml file

| Variable Name | Default Value | Description |
| ---| --- | --- |
| metadata name | mysite-config | metadata name |
| data PORT | 8000 | Port used | 
| data STUDENT_NAME | Dhana | Username | 
| data SITE_NAME | * | Any site name |
| data DEBUG | 1 | Debugging is enabled |
| POSTGRES_DB | mysite | Postgres Database |
| POSTGRES_HOSTNAME | postgres-postgresql | Postgres Host |


# Description of the variables in secret.yaml

| Variable Name | Default Value | Description |
| ---| --- | --- |
| metadata name | mysite-secret | metadata name |  
| SECRET_KEY | "this-is-a-bad-key" | secret key |
| POSTGRES_PASSWORD | "this-is-a-bad-password" | password |
| POSTGRES_USER | mysiteuser | Postgres User |

# Description of the variables in values-postgres.yaml

| Variable Name | Default Value | Description |
| --- | --- | --- |
| username | mysiteuser | Username for Postgres database |
| password | "this-is-a-bad-password" | Postgress password |
| database | mysite | Database Name |

# Deploy your Application
# Make sure you are in the directory where the deployment directory is present
kubectl apply -f deployment/

# Initialization
kubectl exec --stdin --tty pod/mysite-pod -- /bin/bash

python manage.py migrate

python manage.py createsuperuser

# Deletion of the applications created 
kubectl delete service/mysite-svc
kubectl delete pod/mysite-pod
 
