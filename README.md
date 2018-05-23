# multiple_vault_pass
Example Ansible project with multiple vault passwords

### To get started install requirements
``` pipenv install ```

### To run example

Use vault password files:

``` ansible-playbook --vault-id dev@password_dev --vault-id prd@password_prd test.yml ```

Prompt for vault passwords:

``` ansible-playbook --vault-id dev@prompt --vault-id prd@prompt test.yml ```

Expected results:

``` 
TASK [display production password] ***********************************************
ok: [test] => {
    "production": "production"
}

TASK [display development password] **********************************************
ok: [test] => {
    "development": "development"
}
```


### Further Reading

[http://docs.ansible.com/ansible/latest/user_guide/vault.html](http://docs.ansible.com/ansible/latest/user_guide/vault.html)
