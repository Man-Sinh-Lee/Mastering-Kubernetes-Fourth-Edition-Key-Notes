Service accound is used for containers to authenticate with API server.
kubectl create serviceaccount my-service-account

# Use for external access
kubectl create token my-service-token 
k create secret generic my-service-account-secret --from-literal=token="MY-SERVICE-TOKEN OUTPUT HERE"

# User for deployment or pod:
    spec:
      serviceAccount: my-service-account