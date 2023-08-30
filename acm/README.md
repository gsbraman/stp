## ACM

#### Steps Required to Integrate OpenShift GitOps into RHACM "hub" clusterset
Create managed cluster set binding to the namespace where gitops was installed, normally `openshift-gitops`
```
oc create -f managedclustersetbinding.yaml
```
Create placement in the namespace where gitops was installed, normally `openshift-gitops`
```
oc create -f placement-hub-gitops.yaml
```
Create GitOpsCluster CRD
```
oc create -f gitopscluster.yaml
```