
# BITWARDEN KUBERNETES DEPLOYMENT

> This is a highly **experimental** effort to create a Kubernetes deployment around the official Bitwarden Unified (Beta) container image. This is **not** intended for production use!

https://bitwarden.com/help/install-and-deploy-unified-beta/

Create these secrets:

```yaml
apiVersion: v1
kind: Secret
metadata:
    name: bitwarden-db-secret
    namespace: bitwarden
stringData:
    DB_DATABASE: bitwarden
    DB_USERNAME: bitwarden-db-user-here
    DB_PASSWORD: bitwarden-db-pw-here
```

```yaml
# Get these values from https://bitwarden.com/host
apiVersion: v1
kind: Secret
metadata:
    name: bitwarden-install-secret
    namespace: bitwarden
stringData:
    INSTALLATION_ID: install-id-here
    INSTALLATION_KEY: install-key-here
```

You also need to have a valid certificate. You can create a secret of it like so:

```bash
kubectl create secret tls bitwarden-cert-secret --namespace bitwarden --key="tls.key" --cert="tls.crt"
```