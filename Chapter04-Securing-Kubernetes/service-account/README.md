Service accound is used for containers to authenticate with API server.
kubectl create serviceaccount my-service-account

# Use for external access
kubectl create token my-service-token 
k create secret generic my-service-account-secret --from-literal=token="MY-SERVICE-TOKEN OUTPUT HERE"

# User for deployment or pod:
    spec:
      serviceAccount: my-service-account

 service account admission controller: 
 - manages service account
 - assigns default service account if custom service account isn't specified
 - manges ImagePullSecrets, if not, use service account's secret
 - API token for API access added/removed by token controller to var/run/secrets/kubernetes.io/serviceaccount/token