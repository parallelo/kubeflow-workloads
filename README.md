# kubeflow-workloads

## tf-cnn-benchmarks

```
# Start it
cd tensorflow/tf-cnn-benchmarks
kubectl apply -f ./tfjob-cnn-benchmarks-smoketest.yaml

# Check it
kubectl describe -f ./tfjob-cnn-benchmarks-smoketest.yaml

# Verify nodes
kubectl get pods -o=custom-columns=NODE:.spec.nodeName,NAME:.metadata.name | grep tf-smoke

# Grab worker log
kubectl logs tf-smoke-gpu-worker-0 | grep -A 10 'Step'
```
