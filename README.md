# get-started-w-k8s

Repository to test and learn more about k8s

- [get-started-w-k8s](#get-started-w-k8s)
  - [Install Kubectl](#install-kubectl)
  - [Creating a GKE cluster](#creating-a-gke-cluster)

## Install Kubectl

> Reference to install kubectl: <https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/>

## Creating a GKE cluster

All configurations related to cluster access are located [here](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl).

```console
gcloud beta container \
--project "pruebas-301501" clusters create "cluster-1" \
--zone "us-central1-a" \
--no-enable-basic-auth \
--cluster-version "1.21.6-gke.1503" \
--release-channel "regular" \
--machine-type "g1-small" \
--image-type "COS_CONTAINERD" \
--disk-type "pd-standard" \
--disk-size "32" \
--metadata disable-legacy-endpoints=true \
--scopes "https://www.googleapis.com/auth/devstorage.read_only","https://www.googleapis.com/auth/logging.write","https://www.googleapis.com/auth/monitoring","https://www.googleapis.com/auth/servicecontrol","https://www.googleapis.com/auth/service.management.readonly","https://www.googleapis.com/auth/trace.append" \
--max-pods-per-node "3" \
--num-nodes "3" \
--logging=SYSTEM,WORKLOAD \
--monitoring=SYSTEM \
--enable-ip-alias \
--network "projects/pruebas-301501/global/networks/default" \
--subnetwork "projects/pruebas-301501/regions/us-central1/subnetworks/default" \
--no-enable-intra-node-visibility \
--default-max-pods-per-node "110" \
--no-enable-master-authorized-networks \
--addons HorizontalPodAutoscaling,HttpLoadBalancing,GcePersistentDiskCsiDriver \
--enable-autoupgrade \
--enable-autorepair \
--max-surge-upgrade 1 \
--max-unavailable-upgrade 0 \
--enable-shielded-nodes \
--node-locations "us-central1-a"

```
