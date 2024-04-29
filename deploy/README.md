## Build for deploy:

first cd to specific dir, then run:
```
kustomize build . > kubeflow.built.yaml
```

## Optimizations:

Remove the cpu/memory hard requests:
VSCode regexp:
`(\s+)requests:\n\1  cpu: .*\n\1  memory .*\n`

## Deploy to k8s:
```
while ! minikube kubectl -- apply -f deploy/medium/kubeflow.built.yaml ; do sleep 30; done
```
