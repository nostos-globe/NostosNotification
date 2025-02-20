# Notification Service (Notificaciones en Tiempo Real)

## Descripción

El servicio de notificaciones maneja el envío de alertas en tiempo real dentro de la aplicación, tanto por push como por notificaciones internas.

## Características

- Envío de notificaciones push (ejemplo: Firebase Cloud Messaging).
- Envío de notificaciones internas dentro de la app.
- Suscripción a eventos de otros servicios (nuevo\_like, nuevo\_seguidor).
- Uso de NATS o Mosquitto MQTT para manejar notificaciones en tiempo real.
- Integración con Redis para almacenamiento temporal de notificaciones no entregadas.

## Tecnologías Utilizadas

- **Lenguaje**: Go
- **Base de Datos**: PostgreSQL
- **Cache**: Redis
- **Orquestación**: Docker
- **Mensajería**: NATS/MQTT

## Instalación

1. Clona el repositorio:
   ```sh
   git clone <repo-url>
   cd notification-service
   ```
2. Configura las variables de entorno en `.env`.
3. Construye y ejecuta el servicio con Docker:
   ```sh
   docker-compose up --build -d
   ```

## Endpoints

| Método | Ruta                | Descripción                        |
| ------ | ------------------- | ---------------------------------- |
| POST   | /notifications/send | Envía una notificación             |
| GET    | /notifications      | Obtiene notificaciones del usuario |
| DELETE | /notifications/\:id | Elimina una notificación           |

## Seguridad

- Autenticación mediante JWT.
- Validación de permisos para el acceso a notificaciones.
- Uso de Redis para almacenamiento de mensajes no entregados.


