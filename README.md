# Argo-CD를 이용한 GitOps 시스템 구축
출처:https://jennifersoft.com/ko/blog/kubernetes/2023-08-30-jennifer-kubernetes-3/

## 목차

- 기본 용어 설명
- 헬름으로 ArgoCD를 설치
- Port-forward를 이용한 Argo-CD 파드 접속
- Argo-CD를 이용하여 NGINX 헬름 배포

---

### 기본 용어 설명

GitOps

쿠버네티스에서 모든 리소스를 코드를 구현할 수 있었다. 깃옵스는 이러한 코드를 깃(git)에 보관하고 깃에 보관한 코드가 현재 운영 중인 상태(ops)와 동일하게 맞추는 것을 의미한다.

ArgoCD

깃옵스를 구현중 CD에 사용하는 도구, 깃의 코드를 쿠버네티스에 반영을 한다. ArgoCD가 관리하는 작업단위를 application으로 관리를 하는데 application배포를 위해서는 project, k8s-cluster, gti repo, template, k8s-context등의 컨포넌트들을 필요로한다.

- template: 배포할 애플리케이션에 대한 템플릿. yaml, helm, customized등을 지원한다.
