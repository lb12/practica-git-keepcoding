- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
	Mediante "git reset --hard HEAD~1" hacemos un reset del working copy (además del 
	staging area) volviendo a un commit anterior del puntero HEAD actual.

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
	Utilizo "git reflog" para encontrar el id del commit que quiero rehacer y "git reset 
	--hard <id-commit>" para que todo el working copy (además del staging area) modifique 
	su estado a dicho commit.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
	No causó ningún conflicto porque la rama styled estaba al día (up to date) respecto a cualquier cambio 
	hecho en master (el último commit de master ya estaba incluido en la rama de styled) en el git-nuestro.md

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
	Sí hay conflicto ya que hemos modificado mismas lineas en ambas ramas, por lo que debemos resolver a mano este conflicto en git-nuestro.md

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
	No hay conflictos, ya que, aunque en styled hemos estado modificando el archivo git-nuestro.md y en master no hemos actualizado nada sobre este archivo, al absorber master a styled, se actualiza 
	el archivo pero no se produce ningún conflicto.

- ¿Qué comando o comandos utilizaste en el paso 25?
	Para ver el diagrama con las líneas de colores he utilizado el comando "git log --graph". Si se quisiera obtener la info de cada commit en una sola línea y con el diagrama, podríamos haber 
	utilizado "git log --graph --pretty=oneline"

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
	Para hacer el merge no fast forward he utilizado "git merge --no-ff title".

	Podríamos hacer un merge fast-forward con "git merge title", sin problema alguno, ya que el puntero de la rama master solo tendría que apuntar ahora al de la rama title y ya estaría absorbida 
	esta última por master. De hecho, he probado a deshacer el merge --no-ff y a hacer el merge fast forward y, efectivamente, se puede hacer el merge de esta forma.
	
- ¿Qué comando o comandos utilizaste en el paso 27?
	He utilizado el comando "git reset <id_commit>", en mi caso, el id_commit fue 2f0fd77, que he obtenido utilizando el comando "git reflog". Al no utilizar el modificador "--hard" mantenemos en el 
	working copy la modificacion hecha tras el merge.

- ¿Qué comando o comandos utilizaste en el paso 28?
	He utilizado el comando "git checkout git-nuestro.md" para volver al estado inicial de ese commit el archivo git-nuestro.md.

- ¿Qué comando o comandos utilizaste en el paso 29?
	He utilizado el comando "git branch -D title". Utilizo el modificador -D ya que con -d, git nos indica que la rama al no estar mergeada con otra, "perderíamos" los cambios hechos en 
	'title', sabemos que esto no es así, ya que podríamos conocer sus IDs mediante "git reflog".	

- ¿Qué comando o comandos utilizaste en el paso 30?
	He utilizado el comando "git reset --hard 6b14379". Mediante "git reflog" obtengo el id del commit en el que hice el merge "--no-ff".

- ¿Qué comando o comandos usaste en el paso 32?
	Si se trata de que master se situe en el commit inicial:

		Utilizo el comando "git reset --hard <id_commit>"

	Si se trata de que HEAD se situe en el commit inicial:
		Utilizo el comando "git checkout <id_commit>"

	Como entiendo que es master la que se tiene que situar en el commit inicial, utilizo el comando "git reset --hard <id_commit>". El id del commit lo obtengo con git reflog, en mi caso, 22e5565 
	(también podríamos haber utilizado "git log" y hacer el reset al id del commit inicial con el comando "git reset --hard <id_commit>"

- ¿Qué comando o comandos usaste en el punto 33?
	Si se trata de que master se situe en el estado final:

		Utilizo el comando "git reset --hard <id_commit>"

	Si se trata de que HEAD se situe en el estado final:
		Utilizo el comando "git checkout <id_commit>"

	Como entiendo que es master la que se tiene que situar en el estado final, utilizo el comando "git reset --hard <id_commit>". El id del commit lo obtengo con git reflog, en mi caso, 6b14379 
	(también podríamos haber utilizado "git log" e ir directamente al id del commit final con el comando "git reset --hard <id_commit>"

