This folder contains the .yaml files to deploy the ESC VM-Scheduler to Kubernetes.

# via HELM (using artifacthub.io)

tbd

# via HELM (using local files)

1. Set the env variables in the `values.yaml` file

2. Run `helm install -f values.yaml vmscheduler .` or later `helm upgrade -f values.yaml vmscheduler .`

# via kubectl

1. Replace all the env variables with your values

2. Run the following command:
    ```sh
    kubectl apply -f mysqldb-claim0-persistentvolumeclaim.yaml,mysqldb-deployment.yaml,mysqldb-service.yaml,nginx-deployment.yaml,nginx-service.yaml,static-volume-persistentvolumeclaim.yaml,web-claim1-persistentvolumeclaim.yaml,web-deployment.yaml,web-service.yaml
    ```
