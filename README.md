# CB_Repo
CleverBit_Repo

Here are terminal output ;

dell@dell-Latitude-3420:~/Desktop$ kubectl get namespaces
NAME              STATUS   AGE
authority         Active   87m
default           Active   168m
flux-system       Active   162m
istio-ingress     Active   157m
istio-system      Active   157m
kube-node-lease   Active   168m
kube-public       Active   168m
kube-system       Active   168m
servicex          Active   87m
servicey          Active   87m
dell@dell-Latitude-3420:~/Desktop$ kubectl get deployments --all-namespaces
NAMESPACE       NAME                      READY   UP-TO-DATE   AVAILABLE   AGE
authority       authority                 1/1     1            1           87m
flux-system     helm-controller           1/1     1            1           162m
flux-system     kustomize-controller      1/1     1            1           162m
flux-system     notification-controller   1/1     1            1           162m
flux-system     source-controller         1/1     1            1           162m
istio-ingress   istio-ingress             1/1     1            1           20m
istio-system    istio-ingress             0/1     0            0           23m
istio-system    istiod                    1/1     1            1           157m
kube-system     coredns                   1/1     1            1           168m
servicex        servicex                  1/1     1            1           87m
servicey        servicey                  1/1     1            1           87m
dell@dell-Latitude-3420:~/Desktop$ kubectl get svc --all-namespaces
NAMESPACE      NAME                      TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)                                        AGE
authority      authority                 ClusterIP   10.107.90.32     <none>        80/TCP                                         87m
default        kubernetes                ClusterIP   10.96.0.1        <none>        443/TCP                                        168m
flux-system    notification-controller   ClusterIP   10.110.29.37     <none>        80/TCP                                         162m
flux-system    source-controller         ClusterIP   10.96.6.189      <none>        80/TCP                                         162m
flux-system    webhook-receiver          ClusterIP   10.99.94.177     <none>        80/TCP                                         162m
istio-system   istio-ingress             ClusterIP   10.110.96.212    <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   18m
istio-system   istiod                    ClusterIP   10.101.17.149    <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP          157m
kube-system    kube-dns                  ClusterIP   10.96.0.10       <none>        53/UDP,53/TCP,9153/TCP                         168m
servicex       servicex                  ClusterIP   10.111.215.193   <none>        80/TCP                                         87m
dell@dell-Latitude-3420:~/Desktop$ kubectl get pods --all-namespaces
NAMESPACE       NAME                                      READY   STATUS    RESTARTS       AGE
authority       authority-557d4b4d87-gvfrx                1/1     Running   0              87m
flux-system     helm-controller-8555c97646-2lr58          1/1     Running   0              163m
flux-system     kustomize-controller-d676b44b6-82vgw      1/1     Running   0              163m
flux-system     notification-controller-d4748b487-l5q6n   1/1     Running   0              163m
flux-system     source-controller-7454d84978-jd4f6        1/1     Running   0              163m
istio-ingress   istio-ingress-7f5f6f58b8-xrxdc            1/1     Running   0              20m
istio-system    istiod-c58746c74-q8wtr                    1/1     Running   0              157m
kube-system     coredns-7db6d8ff4d-mfxn8                  1/1     Running   0              168m
kube-system     etcd-minikube                             1/1     Running   0              168m
kube-system     kube-apiserver-minikube                   1/1     Running   0              168m
kube-system     kube-controller-manager-minikube          1/1     Running   0              168m
kube-system     kube-proxy-xdfjm                          1/1     Running   0              168m
kube-system     kube-scheduler-minikube                   1/1     Running   0              168m
kube-system     storage-provisioner                       1/1     Running   1 (167m ago)   168m
servicex        servicex-78784f85c-cq757                  1/1     Running   0              87m
servicey        servicey-858997546f-bjws5                 1/1     Running   0              87m
dell@dell-Latitude-3420:~/Desktop$ kubectl get configmaps --all-namespaces
NAMESPACE         NAME                                                   DATA   AGE
authority         authority-config                                       1      88m
authority         istio-ca-root-cert                                     1      88m
authority         kube-root-ca.crt                                       1      88m
default           istio-ca-root-cert                                     1      157m
default           kube-root-ca.crt                                       1      168m
flux-system       istio-ca-root-cert                                     1      157m
flux-system       kube-root-ca.crt                                       1      163m
istio-ingress     istio-ca-root-cert                                     1      157m
istio-ingress     kube-root-ca.crt                                       1      158m
istio-system      istio                                                  2      157m
istio-system      istio-ca-root-cert                                     1      157m
istio-system      istio-gateway-status-leader                            0      157m
istio-system      istio-leader                                           0      157m
istio-system      istio-namespace-controller-election                    0      157m
istio-system      istio-sidecar-injector                                 2      157m
istio-system      kube-root-ca.crt                                       1      158m
kube-node-lease   kube-root-ca.crt                                       1      168m
kube-public       cluster-info                                           2      168m
kube-public       kube-root-ca.crt                                       1      168m
kube-system       coredns                                                1      168m
kube-system       extension-apiserver-authentication                     6      168m
kube-system       kube-apiserver-legacy-service-account-token-tracking   1      168m
kube-system       kube-proxy                                             2      168m
kube-system       kube-root-ca.crt                                       1      168m
kube-system       kubeadm-config                                         1      168m
kube-system       kubelet-config                                         1      168m
servicex          istio-ca-root-cert                                     1      88m
servicex          kube-root-ca.crt                                       1      88m
servicex          servicex-config                                        1      88m
servicey          istio-ca-root-cert                                     1      88m
servicey          kube-root-ca.crt                                       1      88m
servicey          servicey-config                                        1      88m
dell@dell-Latitude-3420:~/Desktop$ kubectl get secrets --all-namespaces
NAMESPACE       NAME                                  TYPE                            DATA   AGE
istio-ingress   cb-tls                                Opaque                          2      46m
istio-ingress   sh.helm.release.v1.istio-ingress.v1   helm.sh/release.v1              1      139m
istio-system    istio-ca-secret                       istio.io/ca-root                5      157m
istio-system    sh.helm.release.v1.istio-base.v1      helm.sh/release.v1              1      157m
istio-system    sh.helm.release.v1.istiod.v1          helm.sh/release.v1              1      157m
kube-system     bootstrap-token-cos4l6                bootstrap.kubernetes.io/token   6      168m
servicex        servicex-secret                       Opaque                          1      88m
servicey        servicex-secret                       Opaque                          1      32m
dell@dell-Latitude-3420:~/Desktop$ kubectl get gateways --all-namespaces
NAMESPACE   NAME                AGE
authority   authority-gateway   88m
servicex    servicex-gateway    88m
dell@dell-Latitude-3420:~/Desktop$ kubectl get virtualservices --all-namespaces
NAMESPACE   NAME        GATEWAYS                HOSTS                            AGE
authority   authority   ["authority-gateway"]   ["authority.cb-interview.com"]   88m
servicex    servicex    ["servicex-gateway"]    ["servicex.cb-interview.com"]    88m
dell@dell-Latitude-3420:~/Desktop$ helm list --all-namespaces
NAME         	NAMESPACE    	REVISION	UPDATED                                	STATUS  	CHART         	APP VERSION
istio-base   	istio-system 	1       	2024-08-02 09:09:36.698336104 +0000 UTC	deployed	base-1.20.0   	1.20.0     
istio-ingress	istio-ingress	1       	2024-08-02 09:28:25.005469219 +0000 UTC	failed  	gateway-1.20.0	1.20.0     
istiod       	istio-system 	1       	2024-08-02 09:10:06.414851435 +0000 UTC	deployed	istiod-1.20.0 	1.20.0     
dell@dell-Latitude-3420:~/Desktop$ kubectl get kustomizations.kustomize.toolkit.fluxcd.io --all-namespaces
NAMESPACE     NAME          AGE    READY   STATUS
flux-system   authority     95m    False   Source is not ready, artifact not found
flux-system   flux-system   161m   False   Source is not ready, artifact not found
flux-system   servicex      95m    False   Source is not ready, artifact not found
flux-system   servicey      74m    False   Source is not ready, artifact not found
dell@dell-Latitude-3420:~/Desktop$ kubectl get helmreleases.helm.toolkit.fluxcd.io --all-namespaces
NAMESPACE       NAME            AGE    READY   STATUS
istio-ingress   istio-ingress   139m   False   install retries exhausted
istio-system    istio-base      159m   True    Release reconciliation succeeded
istio-system    istiod          159m   True    Release reconciliation succeeded
dell@dell-Latitude-3420:~/Desktop$ kubectl get all -n istio-system
NAME                         READY   STATUS    RESTARTS   AGE
pod/istiod-c58746c74-q8wtr   1/1     Running   0          158m

NAME                    TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)                                        AGE
service/istio-ingress   ClusterIP   10.110.96.212   <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   20m
service/istiod          ClusterIP   10.101.17.149   <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP          158m

NAME                            READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/istio-ingress   0/1     0            0           25m
deployment.apps/istiod          1/1     1            1           158m

NAME                                       DESIRED   CURRENT   READY   AGE
replicaset.apps/istio-ingress-558bf5d956   1         0         0       25m
replicaset.apps/istiod-c58746c74           1         1         1       158m

NAME                                         REFERENCE           TARGETS              MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/istiod   Deployment/istiod   cpu: <unknown>/80%   1         5         1          158m
dell@dell-Latitude-3420:~/Desktop$ 

