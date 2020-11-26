#Comados utilizados en la practica para la realización de cada paso.

*** 

1. Crear un repositorio ** Nos situamos en el directorio de nuestro repositorio**
    - git init 

***

2. Crear un archivo git-nuestro.md con el contenido indicado.
    - nano git-nuestro.md
    - Insertamos contenido, cerramos y guardamos.

***

3. Añadir git-nuestro.md al staging area
    - git add git-nuestro.md

***

4. Mover lo que hay en el staging area al repositorio
    - git commit git-nuestro.md

***

5. Crear una rama llamada “styled”
    - git branch styled

***

6. Listar las ramas que hay en el repositorio
    - git branch

***

7. Moverse a la rama “styled”
    - git checkout styled

***

8. Comprobar que se está en la rama correcta 
    - git branch

***

9. Modificar en el archivo git-nuestro.md con el contenido proporcionado.
    - nano git-nuestro.md

***

10. Añadir los cambios al staging area y luego pasarlos al repositorio
    - git add git-nuestro.md
    - got commit git-nuestro.md

***

11. Deshacer el último commit (perdiendo los cambios realizados en el working copy)
    - git reset --hard HEAD~1
	*Usamos el comando reset con --hard ya que no es necesario guardar los cambios del workin copy*	

***

12. Rehacer el último commit (el que acabamos de deshacer)
    - git reflog *Para ver lo que ha sucedido en mi repositorio y buscar el id del commit que queremos rehacer*
    - git reset ---hard 519856f 
          *Rehacemos el commnit con el id escrito y volvemos a como estaba el working directory,*
          *ahora el documento esta tuneado con markdown*

***

13. Hacer un merge con ‘master’ (styled absorbe a master)
    -  git merge master

	*Devuelve el mensaje already up to date*

***

14. Volver a la rama master
    - git checkout master


***

15. Crear una nueva rama l lamada “htmlify”
    - git branch htmlify


***

16. Cambiar a la rama htmlify
    - git checkout htmlify


***

17. Modificar en el archivo git-nuestro.md con el contenido proporcionado: 
    - nano git-nuestro.md

***

18. Hacer un commit
    - git add git-nuestro.md
    - git commit git-nuestro.md

***

19. Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)

    - git checkout styled
    - git merge htmlify
        *$ git merge htmlify*
¨       *Auto-merging git-nuestro.md*
        *CONFLICT (content): Merge conflict in git-nuestro.md*
        *Automatic merge failed; fix conflicts and then commit the result.*

    Se genera un conficto, ya que el fichero ha sido modificado en dos ramas
    diferentes, el contenido de ambos no es el mismo, por lo que hay que
    decidir que hacer.

***
    
20. Si hay conflictos, deberemos resolverlos quedándonos con el contenido de la rama “styled”.
    	$ git status
	On branch styled
	You have unmerged paths.
  		(fix conflicts and run "git commit")
  		(use "git merge --abort" to abort the merge)

	Unmerged paths:
 		(use "git add <file>..." to mark resolution)
        	both modified:   git-nuestro.md

	no changes added to commit (use "git add" and/or "git commit -a")

	**Para resolver el conflicto, edito el fichero y me quedo con el contenido de la rama styled**

        - nano git-nuestro.md
        - git add git-muestro.md
	- git commit

***

21. Desde “master”, hacer un merge con “styled”.
    - git checkout master
    - git merge styled

    Fast-forward  

    bash: $: command not found  

    comandos.md    | 166 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++  

    git-nuestro.md |  21 ++++----  

    2 files changed, 176 insertions(+), 11 deletions(-)  

    create mode 100644 comandos.md    


***

22. Crear una rama “title” y cambiarse a esa rama.
    - git branch title
    - git checkout title
    - git branch


*** 

23. Añadir un título ( a tu gusto) al archivo git-nuestro.md y hacer un commit.
    - nano git-nuestro.md
    - git add git-nuestro.md
    - git commit git-nuestro.md

***

24. Volver a la rama master
    - git checkout master

***

25. Dibujar el diagrama

    - gil log --graph

$ git log --graph
* commit 921251200f4334d52aed3ae2baaf92f124538c1f (HEAD -> master, styled)
| Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
| Date:   Thu Nov 26 12:32:40 2020 +0100
|
|     Añadimos  y modificamos notas de comandos hasta el punto 24.
|
*   commit d85768512e1327856c5454d322075132ae98c4fe
|\  Merge: 0ce01f5 e7015f6
| | Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
| | Date:   Thu Nov 26 12:24:15 2020 +0100
| |
| |     Merge branch 'htmlify' into styled
| |
| |     Editamos el fichero git-nuestro.md con nano y nos quedamos con el contenido de la rama styled.
| |
| * commit e7015f609f1f47fa02971b32024cef0590adfb21 (htmlify)
| | Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
| | Date:   Thu Nov 26 11:30:42 2020 +0100
| |
| |     Añadimos formatos HTML al fichero git-nuestro.md
| |
* | commit 0ce01f57ca425ee8b6765ff0ee9a91d57d247b57
| | Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
| | Date:   Tue Nov 24 19:22:16 2020 +0100
| |
| |     Guardado de los comandos usados en la practica 1 de git  v 1.0
| |
* | commit 519856fc10e23e09182f0759d3194cfffc50184c
|/  Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
|   Date:   Tue Nov 24 18:22:48 2020 +0100
|
|       Añadimos formatos con markdown a nuestro archivo.
|
* commit ac00140cbafcbab6be624a6b0f8c8305258550df
  Author: Francisco Sánchez <fco.sanchezgarcia@gmail.com>
  Date:   Tue Nov 24 18:05:21 2020 +0100

      Creación del archivo git-nuestro.md v1.0 Sin formatos.

***

26. Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)
    - git merge --no-ff title

***

27. Deshacer el merge (sin perder los cambios del working copy)
    - git reset HEAD~1

***

28. Descartar los cambios
    - git restore git-nuestro.md

***

29. Eliminar la rama “title”
    - git branch -D title


30. Rehacer el merge que hemos deshecho
    - $ git reset 00b291c    

***

31. Volver a master y eliminar el resto de ramas

    - git branch -D htmlify

    - git branch -D styled

***
32. Volver al commit i nicial cuando se creó el poema
    - git reflog

    - git reset ac00140

    - git restore git-nuestro.md

***

33. Volver al estado final, cuando pusimos título al poema

    - git reflog
 
    - git reset 2ce6c44

    - git restore git-nuestro.md


34.  Crear l os siguientes tags:

    -Primero vemos todos los commit utilizando 
	- git reflog
    - inicial: en el primer commit
      - git reset ac00140
      - git tag initial 
    - styled: modificación del paso 10
      - git reset 519856f
      - git tag styled

    - htmlify: modificación del paso 17-18
      - git reset e7015f6
      - git tag htmlify

    - title: modificación del paso 30
      - $ git reset 2ce6c44
      - git tag title 

***

35. Ir al tag htmlify

    - git reset htmlify
