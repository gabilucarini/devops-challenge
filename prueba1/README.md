El diagrama que realice está planteado para ser utilizado en una nube de AWS.

Route 53 es el que nos va permitir registrar un dominio y direccionar nuestro tráfico. CloudFront nos permite que nuestros archivos quedan en caché en los servidores de AWS lo que no va a dar una baja latencia.

En nuestra VPC vamos a tener configurado el Internet Gateway junto a un Security Group que solo permita los puerto 80 y 443 para qué se puedan conectar los usuarios(trafico exterior).

A nivel de la Región vamos a tener replicado en dos Availabity Zone diferentes la misma infraestructura para ambos. Lo que nos vas a dar una alta disponibilidad en caso de que una de estas zonas se caiga. El tener configurado un Aplication Load Balancer nos va a permitir poder distribuir la carga entre estas zonas.

Utilizando una VPC vamos a darle conectividad a nuestra aplicación internas además esto nos va a permitir dividir en tres subnet dos de forma privada donde vamos a tener ubicados nuestro servicio de base de datos y backend. Esto nos permite que nuestros servicios sean visibles solo entre ellos.
Una subnet pública que no permitirá entregar nuestro servicio de frontend.
Todos nuestras subnet tendrán configurada un Security Group propio.
Dentro de nuestra subnet tanto en Backend o Frontend estaremos ejecutando instancias de ec2 que utilizaran Docker.

Además configuraremos Auto Scaling para poder replicar instancias en caso de una alta demanda.

En cuanto a las bases de datos utilizaremos Amazon RDS para la base de datos SQL y DynamoDB para la base de NoSQL. Estas tendran una replica en la otra Availability Zone lo que nos garatiza tener siempre disponibilidad de datos.

Para consumir los servicios externos utilizaremos NAT Gateway para que los servicios de Backend puede comunicarse al exterior.