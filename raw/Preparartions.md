# Preparations

You need to prepare the following things before installing the ESC Scheduler in a ESC Kubernetes Cluster:

## Kubernetes Cluster
Make sure to have a running K8s Cluster in your ESC tenant network.

- (Optional): Have a storage class defined that can be used for the ESC Scheduler, something like this:
  ```yaml
   volumeClaimSpec:
      storageClassName: nfs-client
      volumeMode: Filesystem
  ```
  Otherwise, the default volume will be used.

- (Optional): Have a service account setup. Otherwise, the `default` service account will be used.
## Management VM

Make sure to have a VM in the customer Network that has:
- Network access to the Kubernetes cluster
- `kubectl` and `helm` installed
- Internet / Artifactory access for the installation of the container images

## SSL/TLS

You need a `.crt` and `.key` certificate file for securing the application with HTTPS.

Either prepare self-signed certificates, or in case of anm available Certificate Authority, the correspondign files. See [here](https://www.ssls.com/knowledgebase/how-to-install-an-ssl-certificate-on-a-nginx-server/) on how to prepare the certificates of a CA for Nginx.

## (Optional) LDAP

If you want to use LDAP, your cluster needs access to the customers LDAP server (AD) aswell.

- (Optional) To enable secure LDAP, make sure to prepare a `.pem` file.
- Prepare the LDAP attributes (Server Uri, BindDn) etc. and create user groups for the VM Scheduler.
  - 1 Group for regular users
  - 1 Group for admin users

## (Optional) oAuth

In case of a federated client, the VM Scheduler needs to connect to vRA via oAuth.
For this, the following preparations need to be made:

- Let your vRA tenant admin create an oAuth client and tell you the client ID and secret