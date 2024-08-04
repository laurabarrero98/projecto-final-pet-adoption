# Proyecto de Registro de Mascotas para Adopción

## Descripción
Este proyecto es una aplicación para gestionar el registro de mascotas disponibles para adopción. Permite agregar, listar, actualizar y eliminar mascotas y propietarios, así como visualizar detalles y asociar mascotas a propietarios. También incluye una API REST para la interacción programática y la documentación de la API con Swagger.

## Funcionalidades

- **Mostrar Mascota por ID**:
  - **Endpoint**: `GET /api/mascotas/{id}`
  - **Descripción**: Devuelve los detalles de una mascota específica por su ID.

- **Mostrar Mascota por Nombre**:
  - **Endpoint**: `GET /api/mascotas?search={nombre}`
  - **Descripción**: Devuelve una lista de mascotas cuyo nombre coincide con el parámetro de búsqueda.

- **Añadir una Mascota**:
  - **Endpoint**: `POST /api/mascotas/crear`
  - **Descripción**: Permite agregar una nueva mascota con los detalles proporcionados en el cuerpo de la solicitud. Además se le puede asignar un propietario de los disponibles en el momento de la creación.

- **Listar todas las mascotas**:
  - **Endpoint**: `GET /api/mascotas`
  - **Descripción**: Devuelve una lista de todas las mascotas registradas. Puede ordenar por ID o nombre.

- **Listar las 20 mascotas más jóvenes**:
  - **Endpoint**: `GET /api/mascotas/mas-jovenes`
  - **Descripción**: Devuelve las 20 mascotas más jóvenes ordenadas por fecha de nacimiento. En caso de haber menos de 20 mascotas, las muestra todas ordenadas por fecha de nacimiento.

- **Borrar una Mascota**:
  - **Endpoint**: `DELETE /api/mascotas/eliminar/{id}`
  - **Descripción**: Elimina una mascota específica por su ID.

- **Añadir Propietario**:
  - **Endpoint**: `POST /api/propietarios/crear`
  - **Descripción**: Permite agregar un nuevo propietario con los detalles proporcionados.

- **Ver Propietarios**:
  - **Endpoint**: `GET /api/propietarios`
  - **Descripción**: Devuelve una lista de todos los propietarios.

- **Ver Propietario por ID**:
  - **Endpoint**: `GET /api/propietarios/{id}`
  - **Descripción**: Devuelve los detalles de un propietario específico por su ID.

- **Asociar Mascotas a Propietarios**:
  - **Descripción**: En el formulario de creación de propietarios, se puede seleccionar mascotas existentes para asignarles un propietario.

## Acceder a la Aplicación:
    - **Interfaz web**: [http://localhost:8080](http://localhost:8080)

## Archivos Importantes

- `application.properties`: Configuración de la base de datos y propiedades de la aplicación.
- `data.sql`: Script para insertar datos de prueba.
- `schema.sql`: Script para definir la estructura de la base de datos.

## Problemas Conocidos

- **Subida de Imágenes de Mascotas**:
  - Actualmente, la funcionalidad para guardar imágenes de mascotas con nombres dinámicos (`mascota{id}.jpg`) no está implementada. Las imágenes deben ser asignadas manualmente como `default.jpg` si no se proporciona una imagen.
  - Se pretendía implementar un sistema de almacenamiento de archivos y actualizar la lógica de carga para gestionar imágenes correctamente.

- **Manejo de Archivos de Imagen**:
  - Las imágenes subidas no se almacenan con el nombre `mascota{id}.jpg` como se había previsto. Actualmente, se utiliza una imagen por defecto para todas las mascotas nuevas sin una imagen específica. Si el usuario intenta subir una imagen, el programa deja de funcionar.

- **Opción de Ver Propietarios**:
  - La opción de ver propietarios actualmente no funciona como se esperaba. Aunque se ha implementado con los métodos adecuados en el controlador y los archivos `.html`, no se listan todos los propietarios con su nombre, email y mascotas asignadas (nombre y foto). Además, la idea era que al hacer clic en el nombre de una mascota, se mostrase toda la información de la mascota.
- **Opción de update**:
  - Faltaria acabar de implementar el update de mascota para poder modificar datos o añadir propietario.
  - Habría que implementar el update de propietario para poder modificar datos y añadir mascotas.
