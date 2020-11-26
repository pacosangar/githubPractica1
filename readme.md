#Practica 1

##Preguntas


- ¿Qué comando utilizaste en el paso 11?  *git reset --hard HEAD~1* 

  ¿Por qué? *No necesitamos que los cambios queden en el working copy. Así modificamos el working copy dejandolo como estaba*
	

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

    - git reflog *Para ver lo que ha sucedido en mi repositorio y buscar el id del commit que queremos rehacer*  

    - git reset ---hard 519856f   

          <p>Rehacemos el commnit con el id escrito y volvemos a como estaba el working directory,
          ahora el documento esta tuneado con markdown</p>

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
   *git branch veo las ramas existentes y la rama en la que nos encontramos *
   *Como estamos situados en la rama styled usamos git merge master y absorbe la rama master*

   <p>Devuelve el mensaje already up to date por lo que todo ha ido bien, no hay conflictos que resolver</p>
   <p>La rama styled ya tiene todos los cambios que hemos realizado en master.</p> 

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
    - git checkout styled
    - git merge htmlify
        *$ git merge htmlify*
¨       *Auto-merging git-nuestro.md*
        *CONFLICT (content): Merge conflict in git-nuestro.md*
        *Automatic merge failed; fix conflicts and then commit the result.*

    <p>Se genera un conficto, ya que el fichero ha sido modificado en dos ramas
    diferentes, el contenido de ambos no es el mismo, por lo que hay que
    decidir que hacer.</p>


- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
   *No el merge no genero ningún conflicto, ya que en master no hemos realizado modificaciones.*

- ¿Qué comando o comandos utilizaste en el paso 25? *git log --graph*

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
  *Si, ya que ambas ramas forman una lista *

- ¿Qué comando o comandos utilizaste en el paso 27? *git reset HEAD~1*

- ¿Qué comando o comandos utilizaste en el paso 28? *git restore git-nuestro.md*

- ¿Qué comando o comandos utilizaste en el paso 29? *git branch -D title*
- ¿Qué comando o comandos utilizaste en el paso 30? *git reset id_commit *  git reset 00b291c 
- ¿Qué comando o comandos usaste en el paso 32? 
    - git reflog

    - git reset ac00140

    - git restore git-nuestro.md

    *Podiamos usar git reset --hard ac00140 y nos habiamos ahorrado el restore ;-) *



- ¿Qué comando o comandos usaste en el punto 33? 
    
    - git reflog
 
    - git reset 2ce6c44

    - git restore git-nuestro.md

    *Podiamos usar git reset --hard 2ce6c44 y nos habiamos ahorrado el restore ;-) *
