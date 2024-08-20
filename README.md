## Workflow with secrets

Useful Gitea workflow for safe decryption of secrets in a .env which might contain sensitive data such usernames,
passwords, API keys, database connection strings and so on. A good use case for this workflow is to use it to provide decrypted
environment variables at runtime to a docker container. For example, `docker run --env-file ./.env ubuntu bash`.

### How to use

Clone or fork the repo and create a .env file containing key/value pairs of environment variables. For
example, `SUPER_SECRET_PASSWORD=bzdBkRzh4F7UYWx5KXjw3TBm`. Then encrypt the .env with `gpg --symmetric --cipher-algo AES256 .env`
choose a passphrase and keep note of it. Make sure to commit and push the encrypted .env.gpg file.

On the Gitea side, go to Settings > Actions > Secrets and create a new secret called SECRET_PASSPHRASE and set it to your
passphrase.