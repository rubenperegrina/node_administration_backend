# administration_backend


# Arrancar proyecto
1. Instalar node.js y NPM.
2. Instalar MongoDB Community Server https://www.mongodb.com/download-center
3. Arrancar MongoDB https://docs.mongodb.com/manual/administration/install-community/
En cada sistema operativo es distinto, por ejemplo en mac es: 'brew services start mongodb-community@4.2' y para pararlo: 'brew services stop mongodb-community@4.2'.
4. Instalar los paquetes necesarios en la carpeta raiz con 'npm i'.
5. Arrancar el proyecto con 'npm start' en la carpeta raiz, debe aparece 'Server listening on port 4000'.

# Como hacer peticiones a la API a través de Postman
https://www.getpostman.com/

**Registrar nuevo usuario**
1. Hacer una petición POST a la url 'http://localhost:4000/users/register'.
2. Seleccionar RAW y formato JSON.
3. Añadir al body: 
{
    "firstName": "Ruben",
    "lastName": "Peregrina",
    "username": "ruben@user.com",
    "password": "123456"
}
4. Debe devolver un '200 OK'.

**Autenticar usuario**

1. Hacer una petición POST a la url 'http://localhost:4000/users/authenticate'.
2. Seleccionar RAW y formato JSON.
3. Añadir al body: 
{
    "username": "ruben@user.com",
    "password": "123456"
}
4. Debe devolver un '200 OK' y un token.

**Obtener lista de usuarios**

1. Hacer una petición GET a la url 'http://localhost:4000/users'.
2. Seleccionar 'Authorization' y cambiar el tipo a 'Bearer Token', pegar el token de la petición anterior en el campo 'Token'.
3. Debe devolver un '200 OK' y un json con todos los usuarios.

**Editar información de usuario**

1. Hacer una petición PUT a la url 'http://localhost:4000/users/id' el 'id' de la url es el usuario que queremos editar, obtenemos su id al autenticarnos o al obtener el listado de usuarios.
2. Seleccionar 'Authorization' y cambiar el tipo a 'Bearer Token', pegar el token de la petición anterior en el campo 'Token'.
3. Añadimos al body los campos que queremos editar, por ejemplo para editar el nombre y el apellido de un usuario:
{
    "firstName": "Ruben2",
    "lastName": "Peregrina2"
}
4. Debe devolver un '200 OK'.
