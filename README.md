## Workflow with secrets

Useful Gitea workflow for safe decryption of secrets in a .env which might contain sensitive data such usernames,
passwords, API keys and so on. A good use case for this workflow is to use it to provide decrypted environment variables at
runtime to a docker container. For example, `docker run --env-file ./.env ubuntu bash`.