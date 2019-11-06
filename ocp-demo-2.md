
Helpful URLs
https://operatorhub.io/
https://catalog.redhat.com/software/containers/search

create project = david-project

Deploying the Web Terminal
=============================================
workloads > pods > add > deploy image
quay.io/openshiftlabs/workshop-terminal:2.4.0
ENV VAR: OC_VERSION=4.0

networking > routes > workshop-terminal
take a look at URL
take a look at workloads > deployment configs
play around and look at resources that have been created.687407

//highlight connection between routes and services ("workshop-terminal")

Exploring the Cluster
============================================
install oc, login
oc login --token=XXXXX --server=https://api.shared-rhpds.rhpds.openshift.opentlc.com:6443

sample oc commands
```
$ oc get projects //sets context
$ oc get pods //pods -smallest unit
$ oc describe pod workshop-terminal-1-kqf5g //compare to gui project > workloads > pods > yaml
$ oc get routes //routes
$ oc get dc //deployment configs
$ oc get svc //service
$ oc get is
```

Notice we don't have admin rights:

```
$ oc get nodes -o wide
$ oc get nodes --show-labels
```


The cluster operator
===============================================

```
$ oc get deployments -n openshift-cluster-version
$ oc get clusterversion
$ oc get clusteroperator
$ oc adm release info --commits
$ oc rsh -n openshift-cluster-version deployments/cluster-version-operator
$ cat /release-manifests/0000_70_console-operator_00-crd.yaml

```

Show Scale up with GUI (Satish K.)
====================================================
project > edit count (notice status updating)
project > click through Overview / Resources to show assets created from simple container.
workloads > depl. configs > events.
```
$ oc get projects //sets context
$ oc project david-project
```

Scaling an OpenShift 4 cluster
==================================================
