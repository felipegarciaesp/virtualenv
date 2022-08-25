# virtualenv
Notas respecto a crear ambientes virtuales, de OpenBootCamp

`py -m venv [nombre`: Para crear ambiente virtual llamado "nombre".
`source [nombre]/Scripts/activate`: Para activar el ambiente virtual llamado "nombre".
`ls -altr`: Para ver que contiene el entorno virtual.

Para crear ambientes virtuales lo mejor será ocupar el comando `pipenv`.

`pipenv shell`: Para crear un entorno virtual cuyo nobre será el nobre de la carpeta en la que estoy.
`exit`: Para salir del entorno virtualcuando ocupamos `pipenv shell`. Es el equivalente a `deactivate`.
`pipenv install [paquete]`: Instala el paquete "paquete" en el entorno virtual.

- `pipenv`nos permite instalar una librería desde un repositorio WEB. Se hace de la siguiente manera:
```
pipenv install -e git+[ruta]
```
- En el ejempo de clases se hizo lo siguiente para instalar la librería `requests`:
```
pipenv install -e git+https://github.com/requests/requests.git#egg=requests
```

`Pipfile`: Es un fichero que contiene los paquetes instalados por `pipenv`.
`Pipfile.lock`: Fichero en formato JSON.

- El `Pipfile.lock` es un fichero que puedo distribuir para que otras personas puedan instalar los paquetes que tengo.

`pipenv lock`: Esto permite hacer un "lock" (bloqueo) al fichero `Pipfile.lock`. Esto es para que yo lo pueda compartir.

- En la terminal bash puedes copiar y pegar un archivo desde otra carpeta con el siguiente comando:

```
(comando se ejecuta en la carpeta de destino)
cp ../[carpeta fuente]/[archivo.extension] .
```
-Del comando anterior recuerda que el ` . ` significa "en esta carpeta".

- `pipenv install --ignore-pipfile`: Crea un proyecto utilizando `pipenv` leyendo/instalando las dependencias de `Pipfile.lock` de forma de reproducir todo el entorno que se expone en `Pipfile`.
- `pipenv graph`: Muestra las dependencias que tengo (las librerías instaladas y la versión de éstas).
- `pipenv uninstall [libreria]`: Elimina una librería.
- `pipenv check`: Para ver si tengo una librería insegura o con fallos conocidos.
- `pip list | grep -i [paquete]`: Esto me permite ver la versión de cualquier "paquete" que tengo instalado.

# Flujo de Trabajo:

1) Ir a la carpeta donde está el código. Se crea la carpeta en caso que no exista.
2) Se tipea `pipenv shell`para crear el entorno virtual.
3) Si se quieren instalar paquetes, se tipea `pip install [paquete]`.
4) Si se hizo el apartado anterior, tipear `pip list` para ver todo lo instalado.
5) Tipear `exit` si quiero salir.
