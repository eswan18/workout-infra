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
