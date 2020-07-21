# k8s-resources

### End Points
```
Below are the container endpoints
http://localhost:8080/health
http://localhost:8080/host
```

### Manual Start A Pod (without using Replication Container)
```
When pod killed it wont be restarted by 
kubectl create -f https://raw.githubusercontent.com/devops-java/k8s-resources/master/pod-manual.yaml
kubectl get pods
curl http://podIp:8080/health
curl http://podId:8080/host

kubectl describe po podName -o yaml
kubectl describe po podName -o json

kubectl get po -o wide
```
### Pod With Labels

```
Labels used to filter the pod.

kubectl create -f https://raw.githubusercontent.com/devops-java/k8s-resources/master/pod-manual-v1.yaml
kubectl get pods

kubectl get po -l env=design
kubectl get po -l 'env'
kubectl get po -l '!env'

framekwork!=spring to select pods with the framework label with any value other than spring
env in (prod,devel) to select pods with the env label set to either prod or devel
env notin (prod,devel) to select pods with the env label set to any value other than prod or devel

kubectl label po spring-boot-web env=debug --overwrite
kubectl get po -l env=design
kubectl get po -l env!=design
```
### Node Selector Labels
```
kubectl create -f https://raw.githubusercontent.com/devops-java/k8s-resources/master/pod-manual-v2.yaml
It selects the node which is having label prod="true"
```
