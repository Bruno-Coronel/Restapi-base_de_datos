# Ejemplos de Llamadas REST API

## GET - Obtener datos

### Obtener una lista
#### Request:
```
[GET] https://reqres.in/api/users?page=2
```
1. [GET] es el método para solicitar datos.

2. https://reqres.in es la dirección url 

3. /api/users es la ruta que especifíca a qué colección se está accediendo, en este caso usuarios.

#### Response:

```json
{
    "page": 2,
    "per_page": 6,
    "total": 12,
    "total_pages": 2,
    "data": [
        {
            "id": 7,
            "email": "michael.lawson@reqres.in",
            "first_name": "Michael",
            "last_name": "Lawson",
            "avatar": "https://reqres.in/img/faces/7-image.jpg"
        },
        {
            "id": 8,
            "email": "lindsay.ferguson@reqres.in",
            "first_name": "Lindsay",
            "last_name": "Ferguson",
            "avatar": "https://reqres.in/img/faces/8-image.jpg"
        },
        {
            "id": 9,
            "email": "tobias.funke@reqres.in",
            "first_name": "Tobias",
            "last_name": "Funke",
            "avatar": "https://reqres.in/img/faces/9-image.jpg"
        },
        {
            "id": 10,
            "email": "byron.fields@reqres.in",
            "first_name": "Byron",
            "last_name": "Fields",
            "avatar": "https://reqres.in/img/faces/10-image.jpg"
        },
        {
            "id": 11,
            "email": "george.edwards@reqres.in",
            "first_name": "George",
            "last_name": "Edwards",
            "avatar": "https://reqres.in/img/faces/11-image.jpg"
        },
        {
            "id": 12,
            "email": "rachel.howell@reqres.in",
            "first_name": "Rachel",
            "last_name": "Howell",
            "avatar": "https://reqres.in/img/faces/12-image.jpg"
        }
    ]
```

El response es devuelto en formato JSON.

### Obtener una entrada en específico

#### Request
```
[GET] https://reqres.in/api/users/2
```
El 2 en `api/users/2`indica el ID de una entrada en específico, para solo obtener la información de esta.

#### Response

```json
{
    "data": {
        "id": 2,
        "email": "janet.weaver@reqres.in",
        "first_name": "Janet",
        "last_name": "Weaver",
        "avatar": "https://reqres.in/img/faces/2-image.jpg"
    }
}
```

Como respuesta, obtenemos los datos correspondientes al ID indicado.

## POST - Enviar datos

### Crear una nueva entrada

#### Request:
```
[POST] https://reqres.in/api/users
```
1. [POST] es el método utilizado para enviar datos y crear una nueva entrada en el servidor.

2. https://reqres.in es la dirección URL del servidor.

3. /api/users es la ruta que especifica la colección de usuarios en la que se va a crear una nueva entrada.

4. El cuerpo de la solicitud contiene los datos que se enviarán para crear el nuevo recurso.

#### Body (enviado con la solicitud):
```json
{
    "name": "morpheus",
    "job": "leader"
}
```
El cuerpo de la solicitud contiene los datos del nuevo usuario que estamos creando, en este caso, un nombre y un trabajo.

#### Response:
```json
{
    "name": "morpheus",
    "job": "leader",
    "id": "542",
    "createdAt": "2024-10-29T15:35:37.870Z"
}
```
El servidor responde con los datos que fueron creados, agregando un ID único y una marca de tiempo (`createdAt`) que indica cuándo fue creado el recurso.

## PUT - Actualizar datos

### Actualizar una entrada existente

#### Request:
```
[PUT] https://reqres.in/api/users/2
```
1. [PUT] es el método utilizado para actualizar completamente los datos de una entrada existente.

2. https://reqres.in es la dirección URL del servidor.

3. /api/users/2 indica que se está actualizando la entrada con el ID 2.

4. El cuerpo de la solicitud contiene los datos que reemplazarán los existentes.

#### Body (enviado con la solicitud):
```json
{
    "name": "morpheus",
    "job": "zion resident"
}
```
El cuerpo de la solicitud contiene los datos actualizados para la entrada.

#### Response:
```json
{
    "name": "morpheus",
    "job": "zion resident",
    "updatedAt": "2024-10-29T15:40:27.263Z"
}
```
El servidor responde con los datos actualizados, junto con una marca de tiempo (`updatedAt`) que indica cuándo se realizó la actualización.

## DELETE - Eliminar datos

### Eliminar una entrada existente

#### Request:
```
[DELETE] https://reqres.in/api/users/2
```
1. [DELETE] es el método utilizado para eliminar una entrada existente.

2. https://reqres.in es la dirección URL del servidor.

3. /api/users/2 indica que se está eliminando la entrada con el ID 2.

#### Response:
```
204 No Content
```
El servidor responde con un código de estado 204, lo que significa que la eliminación fue exitosa, pero no se devuelve ningún contenido.