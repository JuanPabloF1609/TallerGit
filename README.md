# TallerGit

Juan Pablo Florez Soto 2262375
Paso a paso taller de git:

0. Cuenta en Github
Este paso lo omiti ya que yo ya tenia una cuenta creada en github.

1. Configuracion inicial
Aqui en este paso cree mi repositorio llamdo TallerGit con el comando:
git init TallerGit
Tambien se configuro con mi nombre y mi correo:
git config --global user.name "Juan Pablo Florez"
git config --global user.email "juan.florez.soto@correounivalle.edu.co"
Resultado: el resultado obtenido fue que se inicializo mi repositorio local con mi proyecto con la ubicacion donde se guardo: C:/Users/Juan Pablo/TallerGit/.git/ y luego lo configure con mis datos.

3. Creacion de ramas y commits
Antes primero tuve que pararme en el proyecto con el comando:
cd TallerGit
Ya luego pude crear mi rama llamada feature, con el comando:
git checkout -b feature
Resultado: un mensaje que decia que me habia cambiado a la rama feature porque estaba parado en la rama master.
Luego realize 3 commits posicionado en la rama feature:
echo "Texto inicial" > archivo.txt
git add archivo.txt
git commit -m "Commit inicial"

echo "Texto agregado en feature" >> archivo.txt
git commit -am "Segundo commit en feature"

echo "Texto agregado en feature" >> archivo.txt
git commit -am "Tercer commit en feature"

Resultado: El resultado fue que en cada commit se habian insertado y realizado un cambio pero aparecia la advertencia de que se harian el reemplazo.

3. Merge y rebase
Aqui antes de seguir tuve que devolverme a la rama master utilizando el comando:
git checkout -b master
Resultado: mensaje que me habia cambiado a la rama master
luego para hacer la mezcla de los cambio utilize:
git merge feature
Resultado: mensaje diciendo que ya esta actualizado.
git reset --hard HEAD~1
git rebase feature
Resultado: un mensaje diciendo que ya se habia actualizado y rebasado de manera correcta el merge.

4.Uso de cherry-pick y reflog
Aqui se creo una nueva rama llamada hotfix y hacerle cambios con los siguientes comandos:
git checkout -b hotfix
Resultado: mensaje de que me habia cambiado a la rama hotfix.
echo "Corrección urgente" >> archivo.txt
git commit -am "Hotfix"
Resultado: que habia hecho un cambio y se habia ingresado algo
git checkout master
Resultado: que ahora ya estaba posicionado en la rama master.
git cherry-pick hotfix
Resultado: mensaje de que habia hecho una insersion y me dio la fecha de cuando lo hice:
Sun Oct 6 20:08:41 2024 -0500

luego se miro el historial con el comando:
git reflog
Resultado: me aparecio todos los cambios o commits que habia hecho y los movimientos en que rama.

5.Gestion de conflictos
Aqui se creo un conflicto entre dos ramas en la feature y master, utilizando los comandos:
git checkout feature
echo "Cambio en feature" > conflicto.txt
git commit -am "Cambio en feature"
Resultado: um mensaje que decia que el movimiento se iba a hacer en la rama feature y que debia de utilizar un comando para poder incluir el archivo, el comando era: git add conflicto.txt
luego repetir el comando para comitear y ahi si poder hacer el cambio. luego un mensaje que decia crear el modo 100644 del archivo conflicto.txt
git checkout master
echo "Cambio en master" > conflicto.txt
git commit -am "Cambio en master"
Resultado: um mensaje que decia que el movimiento se iba a hacer en la rama master y que debia de utilizar un comando para poder incluir el archivo, el comando era: git add conflicto.txt
luego repetir el comando para comitear y ahi si poder hacer el cambio. luego un mensaje que decia crear el modo 100644 del archivo conflicto.txt

Y por ultimo arreglar los conflictos por medio del comando:
git merge feature
Resultado: un mensaje que decia que habia un conflicto entre los dos archivos, que la fusion habia fallado y que debia de corregir el conflicto y confirmar el resultado.
Entonces utilice el comando:
git add conflicto.txt
y luego el comando:
git commit -am "Solucion conflicto"
Resultado: un mensaje de que en master a8b3973 solucion conflicto se habia cambiado, y asi solucionando el conflicto.
