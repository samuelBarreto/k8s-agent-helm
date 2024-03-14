### Pré-requisitos

## Helm
## minikube
## docker

Se esta for uma instalação nova, adicione o repositório Helm Datadog:



minikube

` 
    minikube start --nodes 3  -p cluster-minikube
`

`
    kubectl get nodes
    kubectl label node <node_name> node-role.kubernetes.io/worker=worker   
`

Helm
Add the Datadog Helm Repository
`
  helm repo add datadog https://helm.datadoghq.com
  helm repo update
`

touch values.yaml - copia - https://github.com/DataDog/helm-charts/blob/main/charts/datadog/values.yaml


não esqueça de colocar sua 
apikey e seu site no arquivo value

value.yaml

apikey:
site:

Deploy Agent with the above configuration file

`
  helm install datadog-agent -f values.yaml datadog/datadog
`

Update Agent with the above file

`
  helm upgrade datadog-agent -f values.yaml datadog/datadog
`