## Build for deploy:

first cd to specific dir, then run:
```
kustomize build . > kubeflow.built.yaml
```

## Deploy to k8s:
`while ! minikube kubectl -- apply -f deploy/medium/kubeflow.built.yaml ; do sleep 30; done`
