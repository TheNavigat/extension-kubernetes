Make sure that the `deploymentStrategyType` is set to `RollingUpdate`.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ${target.attr('steadybit.label')}
spec:
  replicas: 5
  % startHighlight %
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 3
      maxUnavailable: 0
  % endHighlight %
```

### Read More

[Kubernetes Documentation - Deployment Strategy](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#strategy)

---
This advice is powered by [kube-score](https://kube-score.com/).
