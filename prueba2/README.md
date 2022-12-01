Este Docker Compose crea tres contenedores:

- Base de Datos (utiliza una imagen de postgres)

- Backend (utiliza una imagen de python a partir de un Dockerfile)

- Frontend (utiliza una imagen de node a partir de un Dockerfile)

Para poder desplegar estas aplicaciones necesitamos contar con:

- Git
- Docker
- Docker Compose

Siguiendo la documentación oficial https://docs.docker.com/ instalamos Docker y Docker Compose.

Clonamos el repositorio.
Para poder levantar los servicios debemos correr en consola docker-compose -up -d parados en la carpeta donde está ubicado nuestro docker-compose.yaml
Esto es tanto para una PC local como para un servicio de la nube , en caso de estar en AWS debemos contar con ec2.