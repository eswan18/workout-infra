# Workout Infrastructure

This repository owns the kubernetes configuration and other devops work for my Workout App.

One file is not included: `secrets.yaml`. You will need to add one that looks like:

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: application-secrets
type: Opaque
stringData:
  DATABASE_URL: ****redacted****
  APP_SECRET: ****redacted****
  USER_CREATION_SECRET: ****redacted****
```

# Setting up

I did this via minikube and Helm on an M1 Mac. No guarantees I can totally reproduce the setup, but I think these were the steps:

1. Install minikube
2. Start minikube (`minikube start`)
3. Enable the ingress addon (`minikube addons enable ingress`)
4. Install helm (`brew install helm`)

# Starting it up

I set this up using minikube and Helm on an M1 Mac. That seemed to cause some limitations, but these steps should work.

1. Start minikube: `minikube start`
2. `helm install workout-app .`
3. Start a tunnel: `minikube tunnel`
4. `http://localhost:80` should now be available in the browser and via curl, etc.
