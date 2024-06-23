#############################################
# Push de la rama actual
git push origin $rama_actual

#############################################
# Volver a un commit anterior, descartando los cambios
git reset --HARD $SHA1

#############################################
# Ver y descargar Ramas remotas
git remote show origin
# Si hay alguna rama de la cual no tengamos los datos aún
git fetch origin
# Obtener la rama remota
git checkout --track -b $rama origin/$rama
# más simple
git checkout -t origin/$rama

git branch -a
# * master
#   remotes/origin/HEAD -> origin/master
#   remotes/origin/baremacion
#   remotes/origin/bootstrap
#   remotes/origin/fallo_registro
#   remotes/origin/master
git checkout -b baremacion remotes/origin/baremacion
#############################################

# Crear una rama basada en el HEAD
git branch $branch

# Crear una nueva rama basada en el branch $other
git checkout -b $new_branch $other

# Eliminar una rama local
git branch -d $branch

# Eliminar una rama remota
git push origin :$branch

# Cambiar el nombre de una rama
git branch -m $nombre_rama_anterior $nombre_rama_nuevo

#############################################
# Ignorar el salto de línea en Git http://help.github.com/line-endings/
git config --global core.autocrlf input

#############################################
# Copiar un commit determinado a una rama cualquiera
git checkout $rama
git cherry-pick $SHA1

#############################################
# Trabajando con tags

# Ver los tags locales
git tag 

# Añadir un tag
git tag -a v1.2 $SHA1

# Subir tags al repositorio
git push --tags

##############################################
# Deshacer el último commit (sin haber hecho push)
git reset --soft HEAD~1

# Deshacer el último commit (habiendo hecho ya un push)
git revert HEAD

##############################################
# Subir a la rama Commits parciales (los ficheros que no añado se quedan en el stash y se recuperan luego)
git add $file
git commit -m "Mensaje"
git stash
git pull --rebase origin $rama
git push origin rama
git stash pop

# list commits not pushed to the origin yet
git log origin/master..master

# list remote branches that contain $commit
git branch -r --contains $commit

##############################################
# Recuperarse de un desastre 
http://www.bluemangolearning.com/blog/2009/03/recovering-from-a-disastrous-git-rebase-mistake/
