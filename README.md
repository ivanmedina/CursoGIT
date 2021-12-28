### PRIMEROS COMANDOS

```
git --version
git help
git config --global user.name ""
git config --global user.email ""
git config --global -e
git status
git add <name>
git add .
git reset <name>
git reset .
git log
git config core.autocrlf true
git checkout -- . # regresar al ultimo estado
git checkout -- <file> # regresar al ultimo estado solo para el file
git branch 
git branch -m master main # cambiar nombre de una rama
git config --global init.defaultBranch <name>
git commit -am "Agregar y hacer commit"
git status --short
git log --oneline
git log --oneline --decorate -- all --graph

git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"


```

Si una carpeta no va a tener archivos y desea mantenerse, debe contener un archivo llamado .gitkeep


### Alias
```
git config --global alias.s "status --short"
git config --global -e
```

### Ver diff de cambios en el stage
```
git diff --staged
```

### Modificar el ultimo commit
```
git commit --amend -m "Instalaciones.md actualizado"
```

### Agregar archivos al ultimo commit
```
git reset --soft HEAD^
git add .
git commit -m "commit mensaje"
```

### reset hard
```
git reset --hard <commit>
```

### reflog
```
git reflog
git reset --hard <commit>
```

### cambiar nombre a archivos
```
git mv nombre-anterior.md nombre-nuevo.md
```

### Eliminar archivos
```
git rm <archivo>
```

### Ignorar archivos
```
.gitignore
dist / 
```

### Git ramas
```
git checkout -b rama-conflicto
git branch
git branch -d rama-villanos
git checkout master
git merge rama-villanos
git merge rama-villanos

```

### Git Tags
```
git tag -d super-release
git tag
git tag -a v1.0.0 -m "Version 1.0.0 lista"
git tag -a v0.1.0 62c8a10 -m "Version Alfa"
git show v1.0.0 
```

### Git Stash
Es un lugar donde puedes tener todos los cambios que no tienen seguimiento desde el ultimo commit,
al hacer stach regresamos al HEAD.

-- Si despliego los cambios puedo afectar a mis compañeros: 
-- Usa el stash
```
git stash
git status
git stash pop
git stash apply stash@{2}
git stash drop stash@{0}
git stash show stash@{0}
git stash save "Mensaje"
git stash list --stat
git stash clear
```
Se recomienda solo trabajar con un stash o usar ramas.

### Git Rebase
Permite unir y separar commit (squash), solo hacerlos si no son cambios que impactan
Es util para:
- Ordenar commits
- Corregir mensajes de los commits
- Unir commits
- Separar commits

Los commits de la rama master tambien queremos que esten en la rama alternativa
```
git rebase master
git rebase -i HEAD~4
```
