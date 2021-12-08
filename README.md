# a8r-gitops-example

This is the example repo for Ambassador Labs' [DCP Cloud Configuration Analysis](https://www.getambassador.io/docs/cloud/latest/config-analysis/quick-start/).

To use it, check out the [Quick Start](https://www.getambassador.io/docs/cloud/latest/config-analysis/quick-start/) and fork this repo when indicated. Enjoy!

**IMPORTANT:**

- You must be running Edge Stack or Emissary-ingress **2.0.5 or later** to use this 
  example repo.
- The `manifests` directory in this repo uses a _cleartext-only_ `Listener` and `Host`.
  This is **not recommended for production use** but it greatly simplifies the setup for
  the example.

To apply this to your cluster:

```shell
kubectl create namespace gitops-demo && \
kubectl apply -n gitops-demo -f ./manifests
```

at which point you'll be able to 

```shell
curl http://$AMBASSADOR_IP/backend/
```

for a Quote of the Moment, where `$AMBASSADOR_IP` is the IP address or hostname of the
load balancer for your Edge Stack or Emissary-ingress.
 