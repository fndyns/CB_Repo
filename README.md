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


dell@dell-Latitude-3420:~/Desktop$ token=$(curl -s https://authority.cb-interview.com/token --resolve authority.cb-interview.com:443:127.0.0.1)

dell@dell-Latitude-3420:~/Desktop$ curl https://servicex.cb-interview.com/x --resolve servicex.cb-interview.com:443:127.0.0.1 --header "Authorization: Bearer $token"
curl: (7) Failed to connect to servicex.cb-interview.com port 443 after 0 ms: Connection refused
dell@dell-Latitude-3420:~/Desktop$ 

# Although I have worked hard to solve authentication issue. I couldnt solve it. I tried to make the same cert usage for istio ingress and istiod by copying the cert from one to another, it didnt solve the issue. I also tried to have tokens within istio ingress pod just as in istiod pod, it also didnt solve issue. Here is the current status of the issue ;





NAME                                         REFERENCE           TARGETS              MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/istiod   Deployment/istiod   cpu: <unknown>/80%   1         5         1          158m
dell@dell-Latitude-3420:~/Desktop$ 

dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ 
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl exec -it istio-ingress-85bb545b6c-v4bf6 -n istio-system -- ls /var/run/secrets/tokens
kubectl exec -it istio-ingress-85bb545b6c-v4bf6 -n istio-system -- cat /var/run/secrets/tokens/istio-token
kubectl exec -it istio-ingress-85bb545b6c-v4bf6 -n istio-system -- ls -l /var/run/secrets/tokens/istio-token
ls: cannot access '/var/run/secrets/tokens': No such file or directory
command terminated with exit code 2
cat: /var/run/secrets/tokens/istio-token: No such file or directory
command terminated with exit code 1
ls: cannot access '/var/run/secrets/tokens/istio-token': No such file or directory
command terminated with exit code 2
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl exec -it istio-ingress-85bb545b6c-v4bf6 -n istio-system -- sh
# 
# cd /var/run/secrets/tokens
sh: 2: cd: can't cd to /var/run/secrets/tokens
# cd var
# cd run/secrets/tokens
sh: 4: cd: can't cd to run/secrets/tokens
# cd run/              
# ls
lock  mount  secrets  systemd
# cd secrets	
# ls
istio  kubernetes.io  workload-spiffe-uds
# cd tokens
sh: 9: cd: can't cd to tokens
# cat tokens
cat: tokens: No such file or directory
# ls
istio  kubernetes.io  workload-spiffe-uds
# pwd
/var/run/secrets
# cd istio
# ls
root-cert.pem
# exit
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ 
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get serviceaccount istio-ingress -n istio-system -o yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"v1","kind":"ServiceAccount","metadata":{"annotations":{"meta.helm.sh/release-name":"istio-ingress","meta.helm.sh/release-namespace":"istio-system"},"labels":{"app":"istio-ingress","app.kubernetes.io/managed-by":"Helm","app.kubernetes.io/name":"istio-ingress","app.kubernetes.io/version":"1.20.0","helm.sh/chart":"gateway-1.20.0","helm.toolkit.fluxcd.io/name":"istio-ingress","helm.toolkit.fluxcd.io/namespace":"istio-system","istio":"ingress"},"name":"istio-ingress","namespace":"istio-system"}}
    meta.helm.sh/release-name: istio-ingress
    meta.helm.sh/release-namespace: istio-system
  creationTimestamp: "2024-08-02T14:10:40Z"
  labels:
    app: istio-ingress
    app.kubernetes.io/managed-by: Helm
    app.kubernetes.io/name: istio-ingress
    app.kubernetes.io/version: 1.20.0
    helm.sh/chart: gateway-1.20.0
    helm.toolkit.fluxcd.io/name: istio-ingress
    helm.toolkit.fluxcd.io/namespace: istio-system
    istio: ingress
  name: istio-ingress
  namespace: istio-system
  resourceVersion: "41209"
  uid: 50535c5c-513d-43e1-a6b1-9de405cfa5f8
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ vim sa-patch.yaml
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl patch serviceaccount istio-ingress -n istio-system --patch "$(cat sa-patch.yaml)"
serviceaccount/istio-ingress patched
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ vim deployment-patch.yaml
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl patch deployment istio-ingress -n istio-system --patch "$(cat deployment-patch.yaml)"
deployment.apps/istio-ingress patched
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl rollout restart deployment istio-ingress -n istio-system
deployment.apps/istio-ingress restarted
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl exec -it istio-ingress-85bb545b6c-v4bf6 -n istio-system -- sh
Error from server (NotFound): pods "istio-ingress-85bb545b6c-v4bf6" not found
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get pods -n istio-system -l app=istio-ingress
NAME                             READY   STATUS    RESTARTS   AGE
istio-ingress-77d568d77b-vs5pb   0/1     Running   0          26s
istio-ingress-784b969d75-c7g6h   0/1     Running   0          32s
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl exec -it istio-ingress-77d568d77b-vs5pb -n istio-system -- sh
# cd var
# cd run
# ls
lock  mount  secrets  systemd
# cd secrets	
# ls
istio  kubernetes.io  tokens  workload-spiffe-uds
# cd tokens
# ls -ltr
total 0
lrwxrwxrwx 1 root root 18 Aug  3 12:59 istio-token -> ..data/istio-token
# ls
istio-token
# cat istio-token
eyJhbGciOiJSUzI1NiIsImtpZCI6IkZJdnhrVUdaNWlkaXdSVkhfM3FkNGprcTRGM3pROVExV2kyY0NPaEJFeDgifQ.eyJhdWQiOlsiaXN0aW8tY2EiXSwiZXhwIjoxNzIyNjkzNTU5LCJpYXQiOjE3MjI2ODk5NTksImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwianRpIjoiYjE1Yzc4ODEtYjM4Yi00ODU2LTgzZTItMTA5MmRlZTVhYjRlIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJpc3Rpby1zeXN0ZW0iLCJub2RlIjp7Im5hbWUiOiJtaW5pa3ViZSIsInVpZCI6IjI2Y2QzM2IwLTA0ZDktNDc2NS04NzhjLTdmYTU3ZmFiNTM5MyJ9LCJwb2QiOnsibmFtZSI6ImlzdGlvLWluZ3Jlc3MtNzdkNTY4ZDc3Yi12czVwYiIsInVpZCI6ImY0ZTE0ZmM5LTEyMDktNDgxNS1iOWRmLWI1MjRkZDQ3MDQ1OCJ9LCJzZXJ2aWNlYWNjb3VudCI6eyJuYW1lIjoiaXN0aW8taW5ncmVzcyIsInVpZCI6IjUwNTM1YzVjLTUxM2QtNDNlMS1hNmIxLTlkZTQwNWNmYTVmOCJ9fSwibmJmIjoxNzIyNjg5OTU5LCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6aXN0aW8tc3lzdGVtOmlzdGlvLWluZ3Jlc3MifQ.U_I5d_CJRomnhFz-_7k5hpCQp0vNr0PJTuebZnaC-IFQexnQGMw461-vP_Eslw8RbGrNm7cnHkllODr2TTDXXpUuI2CrlBvxIrFO_wTlgNFryHxLs7A_bf6eqeenErZxOGLYEjN-XOeT-UoHwN-q2M8OIz74KFZRl4oqzvXusk7E2sGfNqbHm-onLlwqVsg42sEjIYstQ8OrWAmZw92nIBEqq7k9MJJSICPYGGLhHh83qtkptf_nkk7LHLsskWLRITBaZnsBrey3_KODpq8Zyrh61lrdcXzSDP1KMVsj8feERBjrp6aKGULtQjhVsT1l9dCjxoCJH3oH-Fr8lz97tw# exit
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get pods -n istio-system -l app=istio-ingress
NAME                             READY   STATUS    RESTARTS   AGE
istio-ingress-77d568d77b-vs5pb   0/1     Running   0          113s
istio-ingress-784b969d75-c7g6h   0/1     Running   0          119s
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl logs -l app=istio-ingress -n istio-system
2024-08-03T13:00:26.753468Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:00:48.385533Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:00:48.387247Z	warn	xdsproxy	upstream [11] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:00:48.387448Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:00:57.858103Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:00:57.859958Z	warn	xdsproxy	upstream [12] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:00:57.860154Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:01:20.859760Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:01:20.861829Z	warn	xdsproxy	upstream [13] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:01:20.862054Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:00:42.268537Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:00:43.994250Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:00:43.995996Z	warn	xdsproxy	upstream [14] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:00:43.996194Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:00:56.459211Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:00:56.460920Z	warn	xdsproxy	upstream [15] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:00:56.461137Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
2024-08-03T13:01:17.275987Z	info	xdsproxy	connected to upstream XDS server: istiod.istio-system.svc:15012
2024-08-03T13:01:17.277751Z	warn	xdsproxy	upstream [16] terminated with unexpected error rpc error: code = PermissionDenied desc = authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/
2024-08-03T13:01:17.277970Z	warning	envoy config external/envoy/source/extensions/config_subscription/grpc/grpc_stream.h:152	StreamAggregatedResources gRPC config stream to xds-grpc closed: 7, authorization failed: no identities ([spiffe://cluster.local/ns/istio-system/sa/istio-ingress]) matched $(POD_NAMESPACE)/	thread=20
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get pods -n istio-system -l app=istio-ingress
NAME                             READY   STATUS    RESTARTS   AGE
istio-ingress-77d568d77b-vs5pb   0/1     Running   0          2m10s
istio-ingress-784b969d75-c7g6h   0/1     Running   0          2m16s
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ 

dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl describe pod -n istio-system
Name:             istio-ingress-77d568d77b-vs5pb
Namespace:        istio-system
Priority:         0
Service Account:  istio-ingress
Node:             minikube/192.168.49.2
Start Time:       Sat, 03 Aug 2024 15:59:19 +0300
Labels:           app=istio-ingress
                  istio=ingress
                  pod-template-hash=77d568d77b
Annotations:      kubectl.kubernetes.io/restartedAt: 2024-08-03T15:59:19+03:00
Status:           Running
IP:               10.244.0.51
IPs:
  IP:           10.244.0.51
Controlled By:  ReplicaSet/istio-ingress-77d568d77b
Containers:
  istio-proxy:
    Container ID:  docker://9956839f926d3b6586055ce4928b4738f008df0c3339ed81ea9673b0a6ed2735
    Image:         docker.io/istio/proxyv2:1.20.0
    Image ID:      docker-pullable://istio/proxyv2@sha256:19e8ca96e4f46733a3377fa962cb88cad13a35afddb9139ff795e36237327137
    Ports:         15021/TCP, 80/TCP, 443/TCP, 15012/TCP, 15017/TCP
    Host Ports:    0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP
    Args:
      proxy
      router
      --domain
      $(POD_NAMESPACE).svc.cluster.local
      --proxyLogLevel=warning
      --proxyComponentLogLevel=misc:error
      --log_output_level=default:info
    State:          Running
      Started:      Sat, 03 Aug 2024 15:59:19 +0300
    Ready:          False
    Restart Count:  0
    Limits:
      cpu:     2
      memory:  1Gi
    Requests:
      cpu:        100m
      memory:     128Mi
    Readiness:    http-get http://:15021/healthz/ready delay=1s timeout=1s period=2s #success=1 #failure=3
    Environment:  <none>
    Mounts:
      /var/run/secrets/istio from istiod-ca-cert (ro)
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-g65sw (ro)
      /var/run/secrets/tokens from istio-token (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       False 
  ContainersReady             False 
  PodScheduled                True 
Volumes:
  istio-token:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3600
  istiod-ca-cert:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  istio-ca-root-cert
    Optional:    false
  kube-api-access-g65sw:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   Burstable
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type     Reason     Age                      From     Message
  ----     ------     ----                     ----     -------
  Warning  Unhealthy  2m27s (x4467 over 147m)  kubelet  Readiness probe failed: Get "http://10.244.0.51:15021/healthz/ready": dial tcp 10.244.0.51:15021: connect: connection refused


Name:             istio-ingress-784b969d75-c7g6h
Namespace:        istio-system
Priority:         0
Service Account:  istio-ingress
Node:             minikube/192.168.49.2
Start Time:       Sat, 03 Aug 2024 15:59:13 +0300
Labels:           app=istio-ingress
                  istio=ingress
                  pod-template-hash=784b969d75
Annotations:      kubectl.kubernetes.io/restartedAt: 2024-08-03T15:42:18+03:00
Status:           Running
IP:               10.244.0.50
IPs:
  IP:           10.244.0.50
Controlled By:  ReplicaSet/istio-ingress-784b969d75
Containers:
  istio-proxy:
    Container ID:  docker://410a42280fdfc69d05ca66becbf4246738d7756db087438c92257c90788c4dd3
    Image:         docker.io/istio/proxyv2:1.20.0
    Image ID:      docker-pullable://istio/proxyv2@sha256:19e8ca96e4f46733a3377fa962cb88cad13a35afddb9139ff795e36237327137
    Ports:         15021/TCP, 80/TCP, 443/TCP, 15012/TCP, 15017/TCP
    Host Ports:    0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP
    Args:
      proxy
      router
      --domain
      $(POD_NAMESPACE).svc.cluster.local
      --proxyLogLevel=warning
      --proxyComponentLogLevel=misc:error
      --log_output_level=default:info
    State:          Running
      Started:      Sat, 03 Aug 2024 15:59:14 +0300
    Ready:          False
    Restart Count:  0
    Limits:
      cpu:     2
      memory:  1Gi
    Requests:
      cpu:        100m
      memory:     128Mi
    Readiness:    http-get http://:15021/healthz/ready delay=1s timeout=1s period=2s #success=1 #failure=3
    Environment:  <none>
    Mounts:
      /var/run/secrets/istio from istiod-ca-cert (ro)
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-dvv6z (ro)
      /var/run/secrets/tokens from istio-token (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       False 
  ContainersReady             False 
  PodScheduled                True 
Volumes:
  istio-token:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3600
  istiod-ca-cert:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  istio-ca-root-cert
    Optional:    false
  kube-api-access-dvv6z:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   Burstable
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type     Reason     Age                      From     Message
  ----     ------     ----                     ----     -------
  Warning  Unhealthy  2m33s (x4468 over 147m)  kubelet  Readiness probe failed: Get "http://10.244.0.50:15021/healthz/ready": dial tcp 10.244.0.50:15021: connect: connection refused


Name:             istiod-c58746c74-q8wtr
Namespace:        istio-system
Priority:         0
Service Account:  istiod
Node:             minikube/192.168.49.2
Start Time:       Fri, 02 Aug 2024 12:10:07 +0300
Labels:           app=istiod
                  install.operator.istio.io/owning-resource=unknown
                  istio=pilot
                  istio.io/rev=default
                  operator.istio.io/component=Pilot
                  pod-template-hash=c58746c74
                  sidecar.istio.io/inject=false
Annotations:      ambient.istio.io/redirection: disabled
                  prometheus.io/port: 15014
                  prometheus.io/scrape: true
                  sidecar.istio.io/inject: false
Status:           Running
IP:               10.244.0.45
IPs:
  IP:           10.244.0.45
Controlled By:  ReplicaSet/istiod-c58746c74
Containers:
  discovery:
    Container ID:  docker://ef811b73646b22c0f93988d41b97d7e72481da3c655e85742cdb5f474fa574d1
    Image:         docker.io/istio/pilot:1.20.0
    Image ID:      docker-pullable://istio/pilot@sha256:da619cc0915a27988ba8357916d84b4a137253a9df967e6521b14dc7100bb246
    Ports:         8080/TCP, 15010/TCP, 15017/TCP
    Host Ports:    0/TCP, 0/TCP, 0/TCP
    Args:
      discovery
      --monitoringAddr=:15014
      --log_output_level=default:info
      --domain
      cluster.local
      --keepaliveMaxServerConnectionAge
      30m
    State:          Running
      Started:      Sat, 03 Aug 2024 13:28:01 +0300
    Last State:     Terminated
      Reason:       Error
      Exit Code:    255
      Started:      Fri, 02 Aug 2024 18:05:49 +0300
      Finished:     Sat, 03 Aug 2024 13:27:51 +0300
    Ready:          True
    Restart Count:  2
    Requests:
      cpu:      500m
      memory:   2Gi
    Readiness:  http-get http://:8080/ready delay=1s timeout=5s period=3s #success=1 #failure=3
    Environment:
      REVISION:               default
      JWT_POLICY:             third-party-jwt
      PILOT_CERT_PROVIDER:    istiod
      POD_NAME:               istiod-c58746c74-q8wtr (v1:metadata.name)
      POD_NAMESPACE:          istio-system (v1:metadata.namespace)
      SERVICE_ACCOUNT:         (v1:spec.serviceAccountName)
      KUBECONFIG:             /var/run/secrets/remote/config
      PILOT_TRACE_SAMPLING:   1
      PILOT_ENABLE_ANALYSIS:  false
      CLUSTER_ID:             Kubernetes
      GOMEMLIMIT:             node allocatable (limits.memory)
      GOMAXPROCS:             node allocatable (limits.cpu)
      PLATFORM:               
    Mounts:
      /etc/cacerts from cacerts (ro)
      /var/run/secrets/istio-dns from local-certs (rw)
      /var/run/secrets/istiod/ca from istio-csr-ca-configmap (ro)
      /var/run/secrets/istiod/tls from istio-csr-dns-cert (ro)
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-624b5 (ro)
      /var/run/secrets/remote from istio-kubeconfig (ro)
      /var/run/secrets/tokens from istio-token (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  local-certs:
    Type:       EmptyDir (a temporary directory that shares a pod's lifetime)
    Medium:     Memory
    SizeLimit:  <unset>
  istio-token:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  43200
  cacerts:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  cacerts
    Optional:    true
  istio-kubeconfig:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  istio-kubeconfig
    Optional:    true
  istio-csr-dns-cert:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  istiod-tls
    Optional:    true
  istio-csr-ca-configmap:
    Type:      ConfigMap (a volume populated by a ConfigMap)
    Name:      istio-ca-root-cert
    Optional:  true
  kube-api-access-624b5:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   Burstable
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:                      <none>


# Here is latest status of curl output ;

dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get gateway  -A
NAMESPACE   NAME                AGE
authority   authority-gateway   29h
servicex    servicex-gateway    29h

dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get VirtualService -A
NAMESPACE   NAME        GATEWAYS                HOSTS                            AGE
authority   authority   ["authority-gateway"]   ["authority.cb-interview.com"]   29h
servicex    servicex    ["servicex-gateway"]    ["servicex.cb-interview.com"]    29h
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ kubectl get svc -n istio-system 
NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)                                        AGE
istio-ingress   ClusterIP   10.98.51.203    <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   25h
istiod          ClusterIP   10.101.17.149   <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP          30h

dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ token=$(curl -s https://authority.cb-interview.com/token --resolve authority.cb-interview.com:443:127.0.0.1)
dell@dell-Latitude-3420:~/Desktop/CBRepo/CB_Repo/KubernetesTest-main/apps$ curl -v https://servicex.cb-interview.com/x --resolve servicex.cb-interview.com:443:10.98.51.203 --header "Authorization: Bearer $token"
* Added servicex.cb-interview.com:443:10.98.51.203 to DNS cache
* Hostname servicex.cb-interview.com was found in DNS cache
*   Trying 10.98.51.203:443...

# I solved istio-ingress pod issue by adding POD_NAMESPACE env into the deployment of istio-ingress ;

        env:
        - name: POD_NAMESPACE
          valueFrom:
            fieldRef:
              fieldPath: metadata.namespace

# Then pod went up ;

dell@dell-Latitude-3420:~$ kubectl get  all -A
NAMESPACE       NAME                                          READY   STATUS    RESTARTS      AGE
authority       pod/authority-557d4b4d87-gvfrx                1/1     Running   3 (63m ago)   2d1h
flux-system     pod/helm-controller-8555c97646-2lr58          1/1     Running   5 (62m ago)   2d3h
flux-system     pod/kustomize-controller-d676b44b6-82vgw      1/1     Running   7 (62m ago)   2d3h
flux-system     pod/notification-controller-d4748b487-l5q6n   1/1     Running   5 (62m ago)   2d3h
flux-system     pod/source-controller-7454d84978-jd4f6        1/1     Running   5 (63m ago)   2d3h
istio-ingress   pod/istio-ingress-7f5f6f58b8-xrxdc            1/1     Running   3 (63m ago)   2d
istio-system    pod/istio-ingress-7dfb5db76f-tz7rg            1/1     Running   0             33m
istio-system    pod/istiod-c58746c74-q8wtr                    1/1     Running   3 (63m ago)   2d3h
kube-system     pod/coredns-7db6d8ff4d-mfxn8                  1/1     Running   3 (63m ago)   2d3h
kube-system     pod/etcd-minikube                             1/1     Running   3 (63m ago)   2d3h
kube-system     pod/kube-apiserver-minikube                   1/1     Running   3 (63m ago)   2d3h
kube-system     pod/kube-controller-manager-minikube          1/1     Running   3 (63m ago)   2d3h
kube-system     pod/kube-proxy-xdfjm                          1/1     Running   3 (63m ago)   2d3h
kube-system     pod/kube-scheduler-minikube                   1/1     Running   3 (63m ago)   2d3h
kube-system     pod/storage-provisioner                       1/1     Running   8 (62m ago)   2d3h
servicex        pod/servicex-78784f85c-cq757                  1/1     Running   3 (63m ago)   2d1h
servicey        pod/servicey-858997546f-bjws5                 1/1     Running   3 (63m ago)   2d1h

NAMESPACE       NAME                              TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)                                        AGE
authority       service/authority                 ClusterIP   10.107.90.32     <none>        80/TCP                                         2d1h
default         service/kubernetes                ClusterIP   10.96.0.1        <none>        443/TCP                                        2d3h
flux-system     service/notification-controller   ClusterIP   10.110.29.37     <none>        80/TCP                                         2d3h
flux-system     service/source-controller         ClusterIP   10.96.6.189      <none>        80/TCP                                         2d3h
flux-system     service/webhook-receiver          ClusterIP   10.99.94.177     <none>        80/TCP                                         2d3h
istio-ingress   service/istio-ingress             ClusterIP   10.110.111.235   <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   46h
istio-system    service/istio-ingress             ClusterIP   10.98.51.203     <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   46h
istio-system    service/istiod                    ClusterIP   10.101.17.149    <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP          2d3h
kube-system     service/kube-dns                  ClusterIP   10.96.0.10       <none>        53/UDP,53/TCP,9153/TCP                         2d3h
servicex        service/servicex                  ClusterIP   10.111.215.193   <none>        80/TCP                                         2d1h

NAMESPACE     NAME                        DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR            AGE
kube-system   daemonset.apps/kube-proxy   1         1         1       1            1           kubernetes.io/os=linux   2d3h

NAMESPACE       NAME                                      READY   UP-TO-DATE   AVAILABLE   AGE
authority       deployment.apps/authority                 1/1     1            1           2d1h
flux-system     deployment.apps/helm-controller           1/1     1            1           2d3h
flux-system     deployment.apps/kustomize-controller      1/1     1            1           2d3h
flux-system     deployment.apps/notification-controller   1/1     1            1           2d3h
flux-system     deployment.apps/source-controller         1/1     1            1           2d3h
istio-ingress   deployment.apps/istio-ingress             1/1     1            1           2d
istio-system    deployment.apps/istio-ingress             1/1     1            1           46h
istio-system    deployment.apps/istiod                    1/1     1            1           2d3h
kube-system     deployment.apps/coredns                   1/1     1            1           2d3h
servicex        deployment.apps/servicex                  1/1     1            1           2d1h
servicey        deployment.apps/servicey                  1/1     1            1           2d1h

NAMESPACE       NAME                                                DESIRED   CURRENT   READY   AGE
authority       replicaset.apps/authority-557d4b4d87                1         1         1       2d1h
flux-system     replicaset.apps/helm-controller-8555c97646          1         1         1       2d3h
flux-system     replicaset.apps/kustomize-controller-d676b44b6      1         1         1       2d3h
flux-system     replicaset.apps/notification-controller-d4748b487   1         1         1       2d3h
flux-system     replicaset.apps/source-controller-7454d84978        1         1         1       2d3h
istio-ingress   replicaset.apps/istio-ingress-7f5f6f58b8            1         1         1       2d
istio-system    replicaset.apps/istio-ingress-68c74f4659            0         0         0       45h
istio-system    replicaset.apps/istio-ingress-694bfbc597            0         0         0       23h
istio-system    replicaset.apps/istio-ingress-69b69cf756            0         0         0       45h
istio-system    replicaset.apps/istio-ingress-76846cd948            0         0         0       46h
istio-system    replicaset.apps/istio-ingress-77d568d77b            0         0         0       23h
istio-system    replicaset.apps/istio-ingress-784b969d75            0         0         0       23h
istio-system    replicaset.apps/istio-ingress-7dfb5db76f            1         1         1       33m
istio-system    replicaset.apps/istio-ingress-85bb545b6c            0         0         0       23h
istio-system    replicaset.apps/istio-ingress-86c94dcf78            0         0         0       45m
istio-system    replicaset.apps/istio-ingress-cd56cdb64             0         0         0       33m
istio-system    replicaset.apps/istiod-c58746c74                    1         1         1       2d3h
kube-system     replicaset.apps/coredns-7db6d8ff4d                  1         1         1       2d3h
servicex        replicaset.apps/servicex-78784f85c                  1         1         1       2d1h
servicey        replicaset.apps/servicey-858997546f                 1         1         1       2d1h

NAMESPACE       NAME                                                REFERENCE                  TARGETS              MINPODS   MAXPODS   REPLICAS   AGE
istio-ingress   horizontalpodautoscaler.autoscaling/istio-ingress   Deployment/istio-ingress   cpu: <unknown>/80%   1         5         1          2d2h
istio-system    horizontalpodautoscaler.autoscaling/istiod          Deployment/istiod          cpu: <unknown>/80%   1         5         1          2d3h

dell@dell-Latitude-3420:~$ kubectl get  po -A
NAMESPACE       NAME                                      READY   STATUS    RESTARTS      AGE
authority       authority-557d4b4d87-gvfrx                1/1     Running   3 (63m ago)   2d1h
flux-system     helm-controller-8555c97646-2lr58          1/1     Running   5 (62m ago)   2d3h
flux-system     kustomize-controller-d676b44b6-82vgw      1/1     Running   7 (62m ago)   2d3h
flux-system     notification-controller-d4748b487-l5q6n   1/1     Running   5 (62m ago)   2d3h
flux-system     source-controller-7454d84978-jd4f6        1/1     Running   5 (63m ago)   2d3h
istio-ingress   istio-ingress-7f5f6f58b8-xrxdc            1/1     Running   3 (63m ago)   2d
istio-system    istio-ingress-7dfb5db76f-tz7rg            1/1     Running   0             33m
istio-system    istiod-c58746c74-q8wtr                    1/1     Running   3 (63m ago)   2d3h
kube-system     coredns-7db6d8ff4d-mfxn8                  1/1     Running   3 (63m ago)   2d3h
kube-system     etcd-minikube                             1/1     Running   3 (63m ago)   2d3h
kube-system     kube-apiserver-minikube                   1/1     Running   3 (63m ago)   2d3h
kube-system     kube-controller-manager-minikube          1/1     Running   3 (63m ago)   2d3h
kube-system     kube-proxy-xdfjm                          1/1     Running   3 (63m ago)   2d3h
kube-system     kube-scheduler-minikube                   1/1     Running   3 (63m ago)   2d3h
kube-system     storage-provisioner                       1/1     Running   8 (62m ago)   2d3h
servicex        servicex-78784f85c-cq757                  1/1     Running   3 (63m ago)   2d1h
servicey        servicey-858997546f-bjws5                 1/1     Running   3 (63m ago)   2d1h
dell@dell-Latitude-3420:~$ kubectl get  svc -A
NAMESPACE       NAME                      TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)                                        AGE
authority       authority                 ClusterIP   10.107.90.32     <none>        80/TCP                                         2d1h
default         kubernetes                ClusterIP   10.96.0.1        <none>        443/TCP                                        2d3h
flux-system     notification-controller   ClusterIP   10.110.29.37     <none>        80/TCP                                         2d3h
flux-system     source-controller         ClusterIP   10.96.6.189      <none>        80/TCP                                         2d3h
flux-system     webhook-receiver          ClusterIP   10.99.94.177     <none>        80/TCP                                         2d3h
istio-ingress   istio-ingress             ClusterIP   10.110.111.235   <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   46h
istio-system    istio-ingress             ClusterIP   10.98.51.203     <none>        15021/TCP,80/TCP,443/TCP,15012/TCP,15017/TCP   46h
istio-system    istiod                    ClusterIP   10.101.17.149    <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP          2d3h
kube-system     kube-dns                  ClusterIP   10.96.0.10       <none>        53/UDP,53/TCP,9153/TCP                         2d3h
servicex        servicex                  ClusterIP   10.111.215.193   <none>        80/TCP                                         2d1h

# Then I retested curl command. It actually works locally (when ı do run port forwarding on one terminal and run the curl on another terminal) as seen below. However it doesnt work outside meaning that without doing port forwarding to my local.

On first terminal ;

dell@dell-Latitude-3420:~$ kubectl port-forward svc/servicex 8080:80 -n servicex
Forwarding from 127.0.0.1:8080 -> 8080
Forwarding from [::1]:8080 -> 8080
Handling connection for 8080
E0804 14:48:42.545220   38474 portforward.go:398] error copying from local connection to remote stream: writeto tcp4 127.0.0.1:8080->127.0.0.1:51864: read tcp4 127.0.0.1:8080->127.0.0.1:51864: read: connection reset by peer

On second terminal ;

dell@dell-Latitude-3420:~$ token=$(curl -s https://authority.cb-interview.com/token --resolve authority.cb-interview.com:443:127.0.0.1)
curl -v https://localhost:8080/x --header "Authorization: Bearer $token"
*   Trying 127.0.0.1:8080...
* Connected to localhost (127.0.0.1) port 8080 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
* TLSv1.0 (OUT), TLS header, Certificate Status (22):
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* (5454) (IN), , Unknown (72):
* error:0A00010B:SSL routines::wrong version number
* Closing connection 0
curl: (35) error:0A00010B:SSL routines::wrong version number

# But curl is not working without doing port forwarding ;

dell@dell-Latitude-3420:~$ curl -v https://authority.cb-interview.com/token --resolve authority.cb-interview.com:443:127.0.0.1
* Added authority.cb-interview.com:443:127.0.0.1 to DNS cache
* Hostname authority.cb-interview.com was found in DNS cache
*   Trying 127.0.0.1:443...
* connect to 127.0.0.1 port 443 failed: Connection refused
* Failed to connect to authority.cb-interview.com port 443 after 0 ms: Connection refused
* Closing connection 0
curl: (7) Failed to connect to authority.cb-interview.com port 443 after 0 ms: Connection refused





