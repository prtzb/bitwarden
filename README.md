# Bitwarden

These are the configuration files for my personal, self-hosted Bitwarden instance. 

## Preparations
Bitwarden needs valid certificates to run properly. The nginx container handles TLS termination. Put your certificate and key files under the following paths:

- `ssl/cert.crt`
- `ssl/cert.key`

Then, edit the following files with your settings:

- `env/settings.env`
- `env/secret.env` (copy template-secret.env first obviously)


## Run

    docker-compose up -d