# q3
This repository contains Quake3 configuration and deployment files, customized for my specific setup. 

These files are ready for deployment in your preferred **OpenShift** project.

## Configuration

**Modify the Configuration File:**

   The file `01_ocp_q3-config.yaml` is a ConfigMap object that defines the Quake3 server configuration. Adjust the config according to your requirements. It should work out of the box and start maps with added AI bots.

## Deployment

   Deploy the configuration to your OpenShift project using the following commands:

   `oc apply -f https://raw.githubusercontent.com/sqrex/q3/main/01_ocp-q3-config.yaml`


   `oc apply -f https://raw.githubusercontent.com/sqrex/q3/main/02_ocp-q3-deployment.yaml`

## Expose

Expose service and add route:

`oc expose --name web svc/quake`

`oc create route edge web --insecure-policy='Redirect' --service='quake'`

## Additional Info

Source of information:

[QuakeKube repo](https://github.com/criticalstack/quake-kube)

[OpenShift example quake3 tutorial](https://examples.openshift.pub/deploy/workload/quake3/)


Don't forget about:
`/cg_fov 120`
