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

### How to encrypt a string

Command:

``` ansible-vault --encrypt-vault-id=dev --vault-id dev@password_dev encrypt_string ```

Result:

```
Reading plaintext input from stdin. (ctrl-d to end input)
test!vault |
          $ANSIBLE_VAULT;1.2;AES256;dev
          64323330303462316439613232666138346134303937336565633433363837636235393333353765
          3839623762656262666333643666643236363263623435330a366361633437643062343463363336
          34396139303661346631393035333839336463623934613931623231616161646638343735326263
          6364623338366264380a376332666138623066363666656632666661326136363330656461636135
          3533
Encryption successful
```

### Further Reading

[http://docs.ansible.com/ansible/latest/user_guide/vault.html](http://docs.ansible.com/ansible/latest/user_guide/vault.html)
