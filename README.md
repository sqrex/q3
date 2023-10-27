# q3
Quake3 config and deployment files tailored to my needs.
As simple as applying into your chosen openshift project.

1. Modify config file to your needs

01_ocp_q3-config.yaml is a ConfigMap object that specify the quake3 server configuration
Change it to your own needs.
remember about /cg_fov 120 :)

2. Create the project and apply yamls
oc apply -f https://raw.githubusercontent.com/sqrex/q3/main/01_ocp-q3-config.yaml
oc apply -f https://raw.githubusercontent.com/sqrex/q3/main/02_ocp-q3-deployment.yaml

3.  Expose
oc expose --name web svc/quake
oc create route edge web --insecure-policy='Redirect' --service='quake'


More info:
https://github.com/criticalstack/quake-kube
