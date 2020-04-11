# For ...

### Directories

Loop over current directory files \(front-matter .yaml\), find 'date' + copy file with this date in the new file name.

```bash
for f in *; do cp $f $(cat $f | grep 'date:' | cut -c7-16)-$f; done
```

### Kubernetes

* Get k8s pod names and loop over

```bash
PODS=$(kgp -n en-cuisine-staging -o jsonpath='{.items[*].metadata.name}')
for pod in $PODS; do echo "Pod: $pod" && echo "---"; done
```

* Initialisation `KUBECONGIF` variable

```bash
for i in ~/Work/kube/config/*; do export KUBECONFIG=$KUBECONFIG:$i; done
```



