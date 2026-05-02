# Actividad 2.5 – Chat en Tiempo Real

**Programación Avanzada II** | CETI Plantel Tonalá

Aplicación de chat en tiempo real desarrollada con Flask-SocketIO y WebSockets.

## Demo en vivo

https://web-production-d5925.up.railway.app/

## Descripción

Sistema de chat que permite la comunicación en tiempo real entre múltiples usuarios conectados desde cualquier dispositivo con acceso a internet. Utiliza el evento predefinido `message` de Socket.IO para el envío y recepción de mensajes.

## Tecnologías

- **Python / Flask** – servidor web
- **Flask-SocketIO** – comunicación en tiempo real mediante WebSockets
- **Eventlet** – manejo de conexiones concurrentes
- **HTML / CSS / JavaScript** – interfaz del cliente

## Estructura del proyecto

```
├── main.py               # Servidor Flask-SocketIO
├── requirements.txt      # Dependencias Python
├── Procfile              # Configuración de arranque para Railway
└── templates/
    └── chat.html         # Interfaz del chat
```

## Instalación local

```bash
pip install flask flask-socketio eventlet
python main.py
```

Abrir en el navegador: `http://localhost:5000`

## Funcionamiento

1. El servidor escucha conexiones WebSocket en el evento `message`
2. Al recibir un mensaje, lo reenvía a todos los clientes conectados (`broadcast=True`)
3. Los clientes actualizan la interfaz en tiempo real sin recargar la página
