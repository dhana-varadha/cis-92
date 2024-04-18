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
| data DATA_DIR | /data | Directory where data resides |
| data DEBUG | 1 | Debug is enabled |

# Description of the variables in secret.yaml

| Variable Name | Default Value | Description |
| ---| --- | --- |
| metadata name | mysite-secret | metadata name |  
| SECRET_KEY | "this-is-a-bad-key" | secret key |

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
 
