## ACM

#### Steps Required to Integrate OpenShift GitOps into RHACM "hub" clusterset
Create ManagedClusterSetBinding to the gitops namespace, normally `openshift-gitops`
```
oc create -f managedclustersetbinding.yaml
```
Create placement in the gitops namespace
```
oc create -f placement-hub-gitops.yaml
```
Create GitOpsCluster CRD
```
oc create -f gitopscluster.yaml
```