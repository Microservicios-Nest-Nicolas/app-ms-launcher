# Dev

1. Clonar repositorio
2. Crear un `.env` basado en el `.env.template`
3. Ejecutar el comando `git submodule update --init --recursive` para recontruir los sub-modulos
4. Ejecutar el comando `docker compose up --build`

### Pasos para crear los Git Submodules

1. Crear un nuevo repositorio en GitHub
2. Clonar el repositorio en la máquina local
3. Añadir el submodule, donde `repository_url` es la url del repositorio y `directory_name` es el nombre de la carpeta donde quieres que se guarde el sub-módulo (no debe de existir en el proyecto)

```
git submodule add <repository_url> <directory_name>
```

4. Añadir los cambios al repositorio (git add, git commit, git push)
   Ej:

```
git add .
git commit -m "Add submodule"
git push
```

5. Inicializar y actualizar Sub-módulos, cuando alguien clona el repositorio por primera vez, debe de ejecutar el siguiente comando para inicializar y actualizar los sub-módulos

```
git submodule update --init --recursive
```

6. Para actualizar las referencias de los sub-módulos

```
git submodule update --remote
```

## Importante

Si se trabaja en el repositorio que tiene los sub-módulos, **primero actualizar y hacer push** en el sub-módulo y **después** en el repositorio principal.

Si se hace al revés, se perderán las referencias de los sub-módulos en el repositorio principal y tendremos que resolver conflictos.

## Tecnologías Utilizadas

- **NestJS**: Framework para construir aplicaciones del lado del servidor en Node.js.
- **Docker**: Para la creación y gestión de contenedores.
- **Git Submodules**: Para la gestión de dependencias de repositorios.
- **Git**: Sistema de control de versiones.
- **GitHub**: Plataforma para alojar repositorios de código.
- **dotenv**: Para la gestión de variables de entorno.
- **Docker Compose**: Herramienta para definir y ejecutar aplicaciones multi-contenedor.
- **TypeScript**: Lenguaje de programación utilizado en el desarrollo.
- **NATS**: Un sistema de mensajería basado en eventos que permite la comunicación entre microservicios de manera eficiente y escalable..

### ¿Porque NATS?

NATS (NATS.io) es un sistema de mensajería ligero y de alto rendimiento que se utiliza para la comunicación entre aplicaciones distribuidas.
A continuación, algunas razones para usar NATS:

1. **Bajo Retardo y Alta Velocidad**: NATS está diseñado para ser extremadamente rápido, con baja latencia, lo que lo hace ideal para sistemas en tiempo real.

2. **Simplicidad**: Su arquitectura es simple y fácil de implementar, lo que reduce la complejidad en el desarrollo de aplicaciones distribuidas.

3. **Escalabilidad**: NATS soporta un alto número de conexiones concurrentes y puede escalar horizontalmente para manejar grandes volúmenes de tráfico.

4. **Modelo de Publicación/Suscripción**: Permite una comunicación flexible entre servicios mediante el uso de patrones de publicación/suscripción y solicitudes/respuestas.

5. **Portabilidad**: Es compatible con múltiples lenguajes de programación, lo que facilita la integración en sistemas heterogéneos.

6. **Fiabilidad**: Ofrece características como persistencia de mensajes (en NATS JetStream) y tolerancia a fallos, asegurando la entrega de mensajes en sistemas críticos.

7. **Código Abierto**: NATS es un proyecto de código abierto, lo que permite a los desarrolladores inspeccionar, modificar y contribuir al código base.

8. **Seguridad**: Proporciona soporte para autenticación, autorización y cifrado TLS, garantizando comunicaciones seguras entre servicios.

En resumen, NATS es una solución ideal para construir sistemas distribuidos, microservicios y aplicaciones en tiempo real que requieren comunicación eficiente, escalable y confiable.
