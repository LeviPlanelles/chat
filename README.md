# Servidor de Chat en Python (PSP)

**VIDEO FUNCIONALIDAD**
https://youtu.be/OMbzm-YJ1Zg

**VIDEO EXPLICATIVO CÓDIGO**
https://youtu.be/EmwJFCWFms0

Este proyecto implementa un servidor de chat multihilo utilizando sockets TCP en Python. Es parte del módulo de Programación de Servicios y Procesos (PSP).

## Características

-   **Multihilo:** Maneja múltiples clientes simultáneamente utilizando `threading`.
-   **Broadcast:** Reenvía los mensajes recibidos de un cliente a todos los demás conectados.
-   **Protocolo Simple:** 
    -   Solicita el nombre al cliente al conectarse (`NAME?`).
    -   Soporta comandos básicos de administración.
-   **Logs:** Muestra actividad del servidor (conexiones, mensajes) en la consola o interfaz configurada.

## Requisitos

-   Python 3.x

## Instalación

No se requiere instalación de librerías externas, ya que utiliza la librería estándar de Python (`socket`, `threading`).

1.  Clona el repositorio o descarga el archivo `chat_server.py`.

## Uso

Para iniciar el servidor, ejecuta el script desde la terminal:

```bash
python3 chat_server.py
```

Por defecto, el servidor escuchará en:
-   **Host:** `0.0.0.0` (todas las interfaces)
-   **Puerto:** `5050`

Puedes modificar las variables `DEFAULT_HOST` y `DEFAULT_PORT` en el código si necesitas cambiar la configuración predeterminada.

## Protocolo de Conexión

1.  El cliente se conecta al socket del servidor.
2.  El servidor envía la cadena `NAME?\n`.
3.  El cliente debe responder con su nombre de usuario seguido de un salto de línea (p.ej., `MiUsuario\n`).
4.  Una vez identificado, cualquier mensaje enviado por el cliente será retransmitido a todos los demás usuarios con el formato `[Nombre]: Mensaje`.

## Estructura del Proyecto

-   `chat_server.py`: Contiene la lógica principal del servidor (clase `ChatServer` y `ClientConn`).

## Notas

Este servidor está diseñado con fines educativos para demostrar el uso de Sockets y Hilos en Python.
