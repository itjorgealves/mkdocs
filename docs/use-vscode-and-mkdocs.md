Activate environment to deploy
``` bash
cd /home/$USER/Documents/mkdocs/
source venv/bin/activate
mkdocs serve
```

Deactivate
``` bash
deactivate
```

Push files to github repo
``` bash
cd /home/$USER/Documents/mkdocs/
git add .
git commit -m $'Adding new cert'
git push origin main
```
