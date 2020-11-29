This folder contains the .yaml files to deploy the ESC VM-Scheduler to Kubernetes.

# via HELM (using the HELM Repository)

1. Add Repository:  
   `helm repo add escvmscheduler https://swisscom.github.io/esc-vm-scheduler-helm-chart`

2. Create a `values.yaml` file and change the values (see [example](https://github.com/swisscom/esc-vm-scheduler-helm-chart/blob/master/raw/values.yaml)) 

3. Install Chart  
   `helm install -f values.yaml my-escvmscheduler escvmscheduler/escvmscheduler`  
    > my-escvmscheduler corresponds to the release name, feel free to change it to suit your needs. You can also add additional flags to the helm install command if you need to.

# via HELM (using local files)

1. Download the GitHub repo

2. Set the env variables in the `values.yaml` file

3. Run `helm install -f values.yaml escvmscheduler .` or later `helm upgrade -f values.yaml vmscheduler .`
