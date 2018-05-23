# multiple_vault_pass
Example Ansible project with multiple vault passwords

## To get started install requirements
``` pipenv install ```

## To run example
``` ansible-playbook --vault-id dev@password_dev --vault-id prd@password_prd test.yml ```
