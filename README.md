## Qubernetes Shortcut
A project for deploying [Quorum](https://github.com/jpmorganchase/quorum) on [Kubernetes](https://github.com/kubernetes/kubernetes).
The project deploys three Quorum-Nodes in one single Kubernetes-Cluster inclusive Quorum’s Transaction Manager tessera. The yaml files were be created with the help of [Qubernetes](https://github.com/jpmorganchase/qubernetes). In addition the project deploys three Epirus-Blockchain-Explorers, one for each node. Therewith you are able to investigate blocks, transactions, contracts on each quorum node. The project helps you to quickly start with your local quorum network. Caution, the project is only for developer environments, not productiv environments!

## Quickstart with minikube
Download and install minikube

## Install
```shell
$> minikube start --memory=8192 --cpus=2 --disk-size="50g"
$> kubectl apply -f ./
$> kubectl config set-context $(kubectl config current-context) --namespace=quorum-test
$> kubectl get pods
$> kubectl logs -f epirus-web-node[n]-xxxxxxxxx-xxxxx
```

## Wait
Wait until you see the line: "Ready on http://localhost:3000" in the epirus-web-node[n]-xxxxxxxxx-xxxxx pods.

## Add hosts to your /etc/hosts file
* Type "minikube ip"
* Add entries with the returned ip from above e.g.  
192.168.64.1		node1.epirus.local  
192.168.64.1		node2.epirus.local  
192.168.64.1		node3.epirus.local  

## Access epirus in your browser
http://node1.epirus.local  
http://node2.epirus.local  
http://node3.epirus.local  