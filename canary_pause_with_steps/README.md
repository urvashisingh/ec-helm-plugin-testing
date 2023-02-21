Chart with weight 30

## Deploying the initial version

To deploy the first version of your application:

```
git clone https://github.com/argoproj/argo-rollouts.git
cd argo-rollouts/examples
helm install example ./canary_pause_with_steps/
```

Your application will be deployed and exposed via the `example-helm-guestbook` service

## Perform the second deployment

To deploy the updated version using a Blue/Green strategy:

```
helm upgrade example ./canary_pause_with_steps/  --set image.tag=0.2
```

Now, two versions will exist in your cluster (and each one has an associated service)

```
kubectl-argo-rollouts get rollout example-helm-guestbook
```

## Promoting the rollout

To advance the rollout and make the new version stable

```
kubectl-argo-rollouts promote example-helm-guestbook
```