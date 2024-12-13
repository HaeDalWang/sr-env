# 고객관리용 Kubectl 컨테이너
고객 클러스터 관리시 로컬 컨테이너를 통해 환경을 분리하여 접근합니다
사용될 계정 정보와 같은 민감 데이터는 볼륨 마운트를 통해서 사용합니다, 절대 컨테이너내 빌드하여 사용하지 않습니다

## 빠른 시작

```
docker run -d --name env-remote svvwac98/sr-env:1.31v2
```

aws config 또는 kubeconfig 등 마운트가 필요할 경우 아래와 같이 예시
```
docker run -d -v /Users/seungdo/salt/ezl/aws:/root/.aws --name env-remote svvwac98/sr-env:1.31v2
```

## 빌드 하여 사용

```
docker build -t <name> .
```

```
docker run --name remote <name>
```

## 기본적으로 설치된 중요 도구 항목
    kubectl 1.31.0
    helm 3.12.0
    terraform 1.10.0
    kubecolor 0.4.0
    kubectx 0.9.5
    awscli 2.22.10
    aws-runas 3.5.2
    ---
    curl
    wget
    git
    jq
    dnsutils
    net-tools
    unzip
    vim
    less