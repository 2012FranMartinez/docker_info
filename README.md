Os muestro de una forma simple y visual los comandos más utilizados a la hora de dockerizar una aplicación. 

# Consejos previos:

- Tener cuenta en DockerHub
- Tener descargada la aplicación Docker Desktop (y tenerlo abierto en local)
- Conectarlo desde terminal y seguir los pasos:

```python
docker login
```

# Comandos básicos:

# [Imágenes]

## 1. Listar imagenes para ver todas las que tienes

```python
docker images
```

## 2. Borrar imágenes

```python
docker rmi id_imagen
```

## 3. Crear la imagen

Reemplazar

- Usuario: Tu nombre de usuario de docker
- NombreImagen: Poner el nombre que quieras darle a la imagen
- Versión: Poner la que tu quieras (es una buena forma de llevar el seguimiento)
- No olvidarse del punto (”.”) del final

```python
docker build -t Usuario/NombreImagen:Versión .
```

# [Contenedores]

## 1. Listar todos los contenedores (inactivos incluidos)

```python
docker ps docker ps -a
```

## 2. Listar contenedores activos

```python
docker ps docker ps
```

## 3. Parar contenedores:

```python
docker stop id_contenedor
```

## 4. Iniciar contenedores

```python
docker start id_contenedor
```

## 5. Borrar contenedores (Borrar antes las imagenes sin y después contenedores)

ATENCIÓN! Debes borrar la imagen antes sino no te dejará.

```python
docker rm id_contenedor
```

# [DockerHub]

El “github” de docker

## 1. Push DockerHub

- Adaptar como antes.

```python
docker push Usuario/NombreImagen:Versión
```

## 2. Pull DockerHub

- Adaptar como antes.

```python
docker pull Usuario/NombreImagen:Versión
```

# Ejemplo Dockerizar una app

## 0. Teniendo un Dockerfile creado

## 1. Crear img

```python
docker build -t 2012franmartinez/app-model:v1 .
```

## 2. Crear contenedor

```python
docker run -p 5000:5000 -d 2012franmartinez/app-model:v1
```

## 3. Pushear Docker hub

```python
docker push 2012franmartinez/app-model:v1
```
