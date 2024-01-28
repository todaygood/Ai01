# k8sgpt 

https://docs.daocloud.io/blogs/230808-k8sgpt


```bash
[root@pcentos ~]# source  /usr/local/bin/set-proxy.sh 
[root@pcentos ~]# curl -LO https://github.com/k8sgpt-ai/k8sgpt/releases/download/v0.3.26/k8sgpt_amd64.rpm
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:--  0:00:01 --:--:--     0
100 21.9M  100 21.9M    0     0  1938k      0  0:00:11  0:00:11 --:--:-- 2853k
[root@pcentos ~]# sudo rpm -ivh -i k8sgpt_amd64.rpm
Preparing...                          ################################# [100%]
Updating / installing...
   1:k8sgpt-0:0.3.26-1                ################################# [100%]
You have new mail in /var/spool/mail/root
[root@pcentos ~]# 
[root@pcentos ~]# 
[root@pcentos ~]# k8sgpt auth add
Warning: backend input is empty, will use the default value: openai
Warning: model input is empty, will use the default value: gpt-3.5-turbo
Enter openai Key: openai added to the AI backend provider list

[root@pcentos ~]# k8sgpt filters list
Active: 
> Pod
> Deployment
> Service
> Ingress
> CronJob
> ReplicaSet
> PersistentVolumeClaim
> StatefulSet
> Node
> ValidatingWebhookConfiguration
> MutatingWebhookConfiguration
Unused: 
> HTTPRoute
> HorizontalPodAutoScaler
> PodDisruptionBudget
> NetworkPolicy
> Log
> GatewayClass
> Gateway

[root@pcentos ~]# k8sgpt analyze 
Error: initialising kubernetes client: Get "https://192.168.31.247:6443/version": EOF

[root@pcentos ~]# k8sgpt analyze 
AI Provider: AI not used; --explain not set

0 cdi/cdi-apiserver()
- Error: Deployment cdi/cdi-apiserver has 1 replicas but 0 are available

1 cdi/cdi-operator()
- Error: Deployment cdi/cdi-operator has 1 replicas but 0 are available

2 openelb-system/openelb-manager()
- Error: Deployment openelb-system/openelb-manager has 1 replicas but 0 are available

3 kubevirt/virt-controller()
- Error: Deployment kubevirt/virt-controller has 2 replicas but 0 are available

4 kubevirt/virt-operator()
- Error: Deployment kubevirt/virt-operator has 2 replicas but 0 are available

5 cdi/cdi-deployment()
- Error: Deployment cdi/cdi-deployment has 1 replicas but 0 are available

6 cdi/cdi-uploadproxy()
- Error: Deployment cdi/cdi-uploadproxy has 1 replicas but 0 are available

7 default/nfs-client-provisioner()
- Error: Deployment default/nfs-client-provisioner has 1 replicas but 0 are available

8 default/nginx01()
- Error: Deployment default/nginx01 has 3 replicas but 0 are available

9 ingress-nginx/ingress-ingress-nginx-controller()
- Error: Deployment ingress-nginx/ingress-ingress-nginx-controller has 1 replicas but 0 are available

10 kube-system/tigera-operator-848fdf8dc8-fjxrc(Deployment/tigera-operator)
- Error: back-off 5m0s restarting failed container=tigera-operator pod=tigera-operator-848fdf8dc8-fjxrc_kube-system(50afbc10-995a-44b0-9972-2b993f830686)
- Error: the last termination reason is Error container=tigera-operator pod=tigera-operator-848fdf8dc8-fjxrc

11 cdi/cdi-apiserver-74f8b7b87b(cdi-apiserver)
- Error: Internal error occurred: failed calling webhook "rev.object.sidecar-injector.istio.io": failed to call webhook: Post "https://istiod-1-14-6.istio-system.svc:443/inject?timeout=10s": service "istiod-1-14-6" not found



21 cdi/cdi-api(cdi-api)
- Error: Service has no endpoints, expected label cdi.kubevirt.io=cdi-apiserver

22 kubesphere-devops-system/devops-jenkins-agent(devops-jenkins-agent)
- Error: Service has no endpoints, expected label component=devops-jenkins-master

23 kubevirt/virt-exportproxy(virt-exportproxy)
- Error: Service has no endpoints, expected label kubevirt.io=virt-exportproxy

24 cdi/cdi-uploadproxy(cdi-uploadproxy)
- Error: Service has no endpoints, expected label cdi.kubevirt.io=cdi-uploadproxy

25 ingress-nginx/ingress-ingress-nginx-controller-admission(ingress-ingress-nginx-controller-admission)
- Error: Service has no endpoints, expected label app.kubernetes.io/instance=ingress
- Error: Service has no endpoints, expected label app.kubernetes.io/name=ingress-nginx
- Error: Service has no endpoints, expected label app.kubernetes.io/component=controller

26 kubesphere-devops-system/webhook-server-service(webhook-server-service)
- Error: Service has no endpoints, expected label control-plane=s2i-controller-manager

27 cdi/cdi-prometheus-metrics(cdi-prometheus-metrics)
- Error: Service has no endpoints, expected label prometheus.cdi.kubevirt.io=true

28 kubesphere-devops-system/devops-jenkins(devops-jenkins)
- Error: Service has no endpoints, expected label component=devops-jenkins-master

29 kubesphere-devops-system/s2ioperator-metrics-service(s2ioperator-metrics-service)
- Error: Service has no endpoints, expected label controller-tools.k8s.io=1.0
- Error: Service has no endpoints, expected label control-plane=s2i-controller-manager

30 kubesphere-devops-system/s2ioperator-trigger-service(s2ioperator-trigger-service)
- Error: Service has no endpoints, expected label control-plane=s2i-controller-manager
- Error: Service has no endpoints, expected label controller-tools.k8s.io=1.0

31 kubevirt/kubevirt-operator-webhook(kubevirt-operator-webhook)
- Error: Service has no endpoints, expected label kubevirt.io=virt-operator

32 openelb-system/openelb-admission(openelb-admission)
- Error: Service has no endpoints, expected label app=openelb-manager
- Error: Service has no endpoints, expected label control-plane=openelb-manager

33 default/nginx01(nginx01)
- Error: Service has no endpoints, expected label app=nginx01

34 ingress-nginx/ingress-ingress-nginx-controller(ingress-ingress-nginx-controller)
- Error: Service has no endpoints, expected label app.kubernetes.io/component=controller
- Error: Service has no endpoints, expected label app.kubernetes.io/instance=ingress
- Error: Service has no endpoints, expected label app.kubernetes.io/name=ingress-nginx

35 kubesphere-devops-system/devops-apiserver(devops-apiserver)
- Error: Service has no endpoints, expected label app.kubernetes.io/instance=devops
- Error: Service has no endpoints, expected label app.kubernetes.io/name=ks-devops
- Error: Service has no endpoints, expected label devops.kubesphere.io/component=apiserver

36 /datavolume-mutate.cdi.kubevirt.io(cdi-api-datavolume-mutate)
- Error: No active pods found within service cdi-api as mapped to by Mutating Webhook datavolume-mutate.cdi.kubevirt.io

37 /mutating.eip.network.kubesphere.io(openelb-admission)
- Error: No active pods found within service openelb-admission as mapped to by Mutating Webhook mutating.eip.network.kubesphere.io

38 /dataimportcron-validate.cdi.kubevirt.io(cdi-api-dataimportcron-validate)
- Error: No active pods found within service cdi-api as mapped to by Validating Webhook dataimportcron-validate.cdi.kubevirt.io

39 /datavolume-validate.cdi.kubevirt.io(cdi-api-datavolume-validate)
- Error: No active pods found within service cdi-api as mapped to by Validating Webhook datavolume-validate.cdi.kubevirt.io

40 /populator-validate.cdi.kubevirt.io(cdi-api-populator-validate)
- Error: No active pods found within service cdi-api as mapped to by Validating Webhook populator-validate.cdi.kubevirt.io

41 /cdi-validate.cdi.kubevirt.io(cdi-api-validate)
- Error: No active pods found within service cdi-api as mapped to by Validating Webhook cdi-validate.cdi.kubevirt.io

42 /validate.nginx.ingress.kubernetes.io(ingress-ingress-nginx-admission)
- Error: No active pods found within service ingress-ingress-nginx-controller-admission as mapped to by Validating Webhook validate.nginx.ingress.kubernetes.io

43 /validate.eip.network.kubesphere.io(openelb-admission)
- Error: No active pods found within service openelb-admission as mapped to by Validating Webhook validate.eip.network.kubesphere.io

44 /kubevirt-create-validator.kubevirt.io(virt-operator-validator)
- Error: No active pods found within service kubevirt-operator-webhook as mapped to by Validating Webhook kubevirt-create-validator.kubevirt.io

45 /objecttransfer-validate.cdi.kubevirt.io(objecttransfer-api-validate)
- Error: No active pods found within service cdi-api as mapped to by Validating Webhook objecttransfer-validate.cdi.kubevirt.io

46 /kubevirt-validator.kubevirt.io(virt-operator-validator)
- Error: No active pods found within service kubevirt-operator-webhook as mapped to by Validating Webhook kubevirt-validator.kubevirt.io

47 /kubevirt-update-validator.kubevirt.io(virt-operator-validator)
- Error: No active pods found within service kubevirt-operator-webhook as mapped to by Validating Webhook kubevirt-update-validator.kubevirt.io


[root@pcentos ~]# 

```



