# DataSaker Agent

## How to user DataSaker Helm repository
```shell
helm repo add datasaker https://datasaker.github.io/agent-helm/
helm repo update
```

## Installing the DataSaker Chart
```shell
helm install datasaker datasaker/agent-helm -n datasaker --create-namespace  \
  --set dataSaker.apiKey=<API_KEY> \
  --set dataSaker.clusterId=<CLUSTER_ID> \
  --set dataSaker.runtimeType=<RUNTIME_TYPE> \
  --set dataSaker.runtimeSock=<RUNTIME_SOCK>
```