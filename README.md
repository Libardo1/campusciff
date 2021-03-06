# campusciff
Repositorio para las prácticas del módulo Data Science ToolKit, Máster Executive en Big Data y Business Analytics

### Comandos utilizados y descripción

1. Creo desde github un repositorio llamado campusciff. Se marca la opción para crear automáticamente un README.md. Además, desde la terminal, creo en mi equipo un directorio llamado ejercicio y accedo a él, inicializando el repositorio.
	```sh
	$ mkdir ejercicio
	$ cd ejercicio
	$ git init
	```	

2. Clono el repositorio remoto (se trae el README.md)

	```sh
	$ git clone git@github.com:goaluix/campusciff.git
	```

3. Subo al stage
	```sh
	$ git add .
	```
4. Commit inicial
	```sh
	$ git commit -m "commit inicial"
	```

5. Creo archivo y carpeta privada
	```sh
	$ echo "contraseña 1234" > privado.txt
	$ mkdir privada
	```

6. Abro el editor vi y creo el archivo .gitignore con dos líneas para que se ignoren ese archivo y carpeta
	![alt text](https://github.com/goaluix/campusciff/blob/master/captura_vi.png "Editor vi")

7. Creo 1.txt
	```sh
	$ echo "One" > 1.txt
	```

8. Subo .gitignore y 1.txt
	```sh
	$ git add .
	$ git commit -m "añadido .gitignore"
	```
9. Actualizo README.md (Esto se hará recurrentemente, según vaya actualizando la documentación)
	```sh
	$ git add .
	$ git commit -m "actulizado README.md"
	```

10. Creo y subo etiquetas
	```sh
	$ git tag v0.1
	$ git push --tag origin master
	``` 
11. Creo rama v0.2 y me posiciono en ella.
	```sh
	$ git branch v0.2
	$ git checkout v0.2
	``` 

12. Compruebo que el head apunta a mi nueva rama. Creo fichero 2.txt y lo subo
	```sh
	$ git log --oneline --decorate --graph --all
	* ac67a3e (HEAD -> v0.2, origin/master, origin/HEAD, master) README.md actualizado
	* e5f5e49 (tag: v0.1) actulizado README.md
	* ef73f30 añadido .gitignore
	* 0253712 commit inicial
	* 2e5d166 Initial commit
	$ echo "dos" > 2.txt
	$ git add .
	$ git commit -m "Añadido 2.txt "
	$ git push origin v0.2
	``` 

13. Me posiciono de nuevo en master y hago merge con v0.2
	```sh
	$ git checkout master
	$ git merge v0.2
	``` 

13. Merge con conflicto. 
	```sh
	$ echo "Hola" >> 1.txt
	$ git add .
	$ git commit -m "añadido hola a 1.txt"
	$ git checkout v0.2

	$ echo "adios" > 1.txt
	$ git add .
	$ git commit -m "añadido adios a 1.txt (v0.2)"

	$ git checkout master
	$ git merge v0.2
	Auto-merging 1.txt
	CONFLICT (content): Merge conflict in 1.txt
	Automatic merge failed; fix conflicts and then commit the result.

	$ cat 1.txt
	<<<<<<< HEAD
	One
	Hola
	=======
	adios
	>>>>>>> v0.2

	$ vi 1.txt
	$ cat 1.txt
	One
	Hola y adios

	$ git add .
	$ git commit -m "conflicto resuelto entre master y v0.2"
	$ git push origin master
	```
14. Creo etiqueta v0.2
	```sh
	$ git tag v0.2
	```
15. Elimino rama v0.2 (en local, para remoto habría que usar además git push alias-repositorio-remoto --delete nombre-rama-remota)
	```sh
	$ git branch -d v0.2
	```
16. Listo los distintos commits
	```sh
$ git log --oneline --decorate --graph --all
* 0d4efd1 (HEAD -> master, origin/master, origin/HEAD) README.md formateado
* 5ae73f0 README.md actualizado
*   f7b1d43 (tag: v0.2) conflicto resuelto entre master y v0.2
|\
| * 25dd144 añadido adios a 1.txt (v0.2)
* | 8befef5 añadido hola a 1.txt
|/
* 03a4977 (origin/v0.2) Añadido 2.txt
* ac67a3e README.md actualizado
* e5f5e49 (tag: v0.1) actulizado README.md
* ef73f30 añadido .gitignore
* 0253712 commit inicial
* 2e5d166 Initial commit
	```
	
17. Poner foto en el perfil. Desde la opción de profile
	![alt text](https://github.com/goaluix/campusciff/blob/master/fotosubida.jpg "Profile github")

18. Doble factor de autenticación. 
	![alt text](https://github.com/goaluix/campusciff/blob/master/auth1.png "Autenticación")
	Eligo sms. Github envía un código para validar.
	![alt text](https://github.com/goaluix/campusciff/blob/master/auth2.png "Autenticación por sms")
	Activado el doble factor de seguridad
	![alt text](https://github.com/goaluix/campusciff/blob/master/auth3.png "Doble factor")

19. Clave pública. Ya estaba añadida
	![alt text](https://github.com/goaluix/campusciff/blob/master/ssh.png "ssh")
	

	
20. Uso social. Sigo a 4 compañeros y repositorios y añado estrellas a sus repositorios
	![alt text](https://github.com/goaluix/campusciff/blob/master/colaborar.png "Uso social")
		
	
21. Tabla con compañeros

	| Nombre | Github |
	| ---------- | ---------- |
	| MiguelCerdan  | https://github.com/MiguelCerdan/campusciff.git   |
	| adiazgalache   | https://github.com/adiazgalache/campusciff.git   |
	| macarenagaranena  | https://github.com/macarenagaranena/campusciff.git   |


22. Colaborador
	![alt text](https://github.com/goaluix/campusciff/blob/master/colaborador.png "Colaborador")
	
	
23. Organización y equipos

	![alt text](https://github.com/goaluix/campusciff/blob/master/colaboradores.png "Colaborador")
	![alt text](https://github.com/goaluix/campusciff/blob/master/administradores.png "Colaborador")

24. index.html

	Creo un repositorio campusciff-goaluix dentro de la organización. Añado un fichero index.html
	```sh
	$ git add .
	$ git commit -m "subido index.html"
	$ git push origin master
	```	
	Ver http://campusciff-goaluix.github.io/
	
25. Pull Requests
	Hago fork de adiazgalache
	![alt text](https://github.com/goaluix/campusciff/blob/master/forkadiaz.png "Fork")
	
	Me clono el repositorio en local, creo una nueva rama, modifico y subo.
	```sh
	mkdir adiaz
	git clone git@github.com:goaluix/campusciff-adiazgalache.github.io.git
	git branch rama2
	git checkout rama2
	echo "Luis Nuño" >> index.html
	git add .
	git commit -m "mi nombre"
	git push origin rama2
	```
	
	Hago pullrequest
		![alt text](https://github.com/goaluix/campusciff/blob/master/pullrequest.png "Pull request")
		![alt text](https://github.com/goaluix/campusciff/blob/master/pullrequest2.png "Pull request")


	Lo mismo para ciffsara





	


	
