#  get started

```
minikube delete && minikube start --vm=true  --kubernetes-version=v1.20.0 --cpus=4  --memory=8g --bootstrapper=kubeadm --extra-config=kubelet.authentication-token-webhook=true --extra-config=kubelet.authorization-mode=Webhook --extra-config=scheduler.address=0.0.0.0 --extra-config=controller-manager.address=0.0.0.0

```


```
minikube addons disable metrics-server
```
**DownLoad**
https://github.com/prometheus-operator/kube-prometheus/releases/tag/v0.8.0


#  Quickstart


```
kubectl create -f manifests/setup
until kubectl get servicemonitors --all-namespaces ; do date; sleep 1; echo ""; done
kubectl create -f manifests/
```


**端口映射**
```
kubectl --namespace monitoring port-forward svc/prometheus-k8s 9090 &

kubectl --namespace monitoring port-forward svc/grafana 3000 &

kubectl --namespace monitoring port-forward svc/alertmanager-main 9093 &


```

##  Grafana / Prometheus / Alert Manager
[http://localhost:3000](http://localhost:3000/)
[http://localhost:9090](http://localhost:9090/)
[http://localhost:9093](http://localhost:9093/)





----

https://medium.com/codex/setup-kuberhealthy-with-prometheus-and-grafana-on-minikube-b2f6da21dc2e



---

##  minikube install  EFK addon


https://minikube.sigs.k8s.io/docs/handbook/addons/custom-images/


```
minikube addons enable efk
```


```
minikube addons enable efk --images="Kibana=kibana/kibana:5.6.2-custom" --registries="Kibana=,Elasticsearch=192.168.10.2:5555,FluentdElasticsearch=192.168.10.2:5555"
```




```
minikube enable EFK addon

minikube addons open efk

minikube service kibana-logging --namespace=kube-system

 
```


# istio 


https://argoproj.github.io/argo-rollouts/getting-started/setup/



https://argoproj.github.io/argo-rollouts/getting-started/setup/#istio


https://ibm.github.io/istio101/

https://ibm.github.io/istio101/exercise-5/

https://meteatamel.wordpress.com/2018/04/24/istio-101-with-minikube/

https://minikube.sigs.k8s.io/docs/handbook/addons/custom-images/




#  skywlking

https://www.tetrate.io/blog/observe-service-mesh-with-skywalking-and-envoy-access-log-service/


----


https://kiali.io/documentation/latest/quick-start/
https://www.tetrate.io/blog/observe-service-mesh-with-skywalking-and-envoy-access-log-service/

https://github.com/apache/skywalking-kubernetes


---

https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes


https://medium.com/codex/setup-kuberhealthy-with-prometheus-and-grafana-on-minikube-b2f6da21dc2e

https://medium.com/codex/setup-kuberhealthy-with-prometheus-and-grafana-on-minikube-b2f6da21dc2e


https://prometheus-operator.dev/



