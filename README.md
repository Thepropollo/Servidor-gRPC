
# Servidor gRPC + API REST

Este proyecto implementa un servicio gRPC para gestionar libros, junto con una API REST construida en Flask que interactúa con el servicio gRPC. Usa SQLite como base de datos.

## 📦 Requisitos

- Python 3.7 o superior
- pip
- Paquetes Python necesarios:
  - grpcio
  - grpcio-tools
  - Flask

Instalación:

```bash
pip install grpcio grpcio-tools flask
```

## 🛠 Generar archivos gRPC desde libros.proto

Si no están presentes `libros_pb2.py` y `libros_pb2_grpc.py`, generarlos con:

```bash
python -m grpc_tools.protoc -I. --python_out=. --grpc_python_out=. libros.proto
```

## ▶️ Ejecutar el servidor gRPC

```bash
python server.py
```

Esto iniciará el servidor gRPC en el puerto `50051`.

## 🌐 Ejecutar la API REST

En otra terminal, ejecutar:

```bash
python api_rest.py
```

Esto levantará la API REST en el puerto `5000`.

## 🧪 Probar la aplicación

Abrir un navegador y acceder a:

```
http://localhost:5000
```

Ahí podrás interactuar con la interfaz web.

## 📁 Estructura del proyecto

```
├── libros.proto               # Definición del servicio gRPC
├── libros_pb2.py              # Generado automáticamente
├── libros_pb2_grpc.py         # Generado automáticamente
├── server.py                  # Servidor gRPC
├── api_rest.py                # API REST (Flask)
├── db.py                      # Manejo de base de datos SQLite
├── libros.db                  # Base de datos
└── templates/
    └── ...                    # Archivos HTML
```

## ⚠️ Notas

- Asegúrate de tener los puertos 50051 y 5000 disponibles.
- Si editas `libros.proto`, vuelve a generar los archivos gRPC.
- La base de datos `libros.db` debe estar en el mismo directorio para que el sistema funcione correctamente.
