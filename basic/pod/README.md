# 파드
## 빠르게 Pod 만들기
- docker run에 익숙한 분들을 위해 kubectl run 명령어를 소개합니다.
```
kubectl run echo --image ghcr.io/subicura/echo:v1

kubectl run echo --image ghcr.io/subicura/echo:v1 --dry-run=client -o yaml > 01-runpod.yaml
```

```
# 파드 목록 조회
k get pod
k get pod -o wide
k get pod -n default

# 단일 파드 상세 확인
k describe pod echo
k describe -n default pod echo

# 단일 파드 제거
k delete pod echo
```

## livenessProbe
- 컨테이너가 정상적으로 동작하는지 체크하고 정상적으로 동작하지 않는다면 컨테이너를 재시작하여 문제를 해결
- 정상을 확인하는 방법