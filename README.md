# DevConf.CZ 2019: Running Apache Kafka on Kubernetes and OpenShift

This repository contains the demos from my talk about [Strimzi Kafka operator](http://strimzi.io) at [DevConf.CZ](https://devconf.info/cz).

* Slides: [Google Docs](https://todo)

## Preparation

* Start your Minishift or `oc cluster up` OpenShfit cluster or connect to some other Kubernets or OpenShift environment
* Login as a cluster admin `oc login -u system:admin`
* Use the namespace `myproject`
* Deploy [Strimzi Kafka operator](http://strimzi.io) using `oc apply -f ./install-strimzi`

## Deployment

* Deploy Kafka the first Kafka cluster: `oc apply -f 01-basic-cluster.yaml`
* See how the cluster deployes pod after pod

## Updates

* Update the Kafka cluster and change the KAfka configuration: `oc apply -f 02-kafka-rolling-update.yaml`
* Watch the rolling update

## Topic and User Operators

* Have a look at [`03-address-book.yaml`](./03-address-book.yaml) and check how it combines topic, user and deployment
* Deploy the application together with the topic and user using `oc apply -f 03-address-book.yaml`

## Off cluster access

* Apply the off cluster access using routes using `oc apply -f 04-kafka-off-cluster-access` and check how are they created