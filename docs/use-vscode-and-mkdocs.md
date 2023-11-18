---
title: "Python virtual environment & GitHub actions"
---

### Activate environment to deploy
``` bash title="Activate environment to deploy" linenums="1" hl_lines="2"
cd /home/$USER/Documents/mkdocs/
source venv/bin/activate
mkdocs serve
```

### Deactivate
``` bash linenums='1'
deactivate
```

### Push files to github repo
``` bash linenums='1'
cd /home/$USER/Documents/mkdocs/
git add .
git commit -m $'New files'
git push origin main
```

!!! Warning
    If error acourr
    ``` bash
    sign_and_send_pubkey: signing failed for "******" from agent: agent refused operation
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.
    
    Please make sure you have the correct access rights
    and the repository exists.
    ```

!!! Note
    If necessarly:
    ``` bash
    # To see fingerprints
    ssh-add -l
    # To add and permit push
    ssh-add
    ```
