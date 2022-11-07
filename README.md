# Kubernetes Agent 설치하기

## User tenant 정보 등록
```shell
# datasaker 디렉토리 생성
mkdir -p ~/datasaker
```
```shell
# datasaker 유저 정보 등록
cat << EOF > ~/datasaker/config.yaml
dataSaker:
  clusterName: $(cluster_name)
  apiKey: $(api_key)
  runtimeType: $(runtime_type)
  runtimeSock: $(runtime_sock)
EOF
```

## helm을 이용하여 agent 설치
```shell
# datasaker helm repo를 추가합니다.
helm repo add datasaker https://datasaker.github.io/agent-helm/
```

```shell
# datasaker helm pull
helm pull datasaker/agent-helm
```

```shell
# 압축 풀기
tar -zxvf agent-helm-0.1.0.tgz -C ~/datasaker
```

```shell
# datasaker kubernetes agent 설치
helm install datasaker ~/datasaker/agent-helm -n datasaker --create-namespace \
  -f ~/datasaker/config.yaml
```
