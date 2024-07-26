# API Documentation

## Endpoints

### Get All Usuarios

- **URL:** `/backend/index.php?action=getAllUsuarios`
- **Method:** `GET`
- **Success Response:**
  - **Code:** 200 OK
  - **Content:**
    ```json
    [
      {
        "id": 1,
        "name": "John Doe"
      },
      {
        "id": 2,
        "name": "Jane Smith"
      }
    ]
    ```
- **Error Response:**
  - **Code:** 400 Bad Request
  - **Content:** `{ "error": "Invalid request" }`

### Get Usuario by ID

- **URL:** `/backend/index.php?action=getUsuarioById&id={id}`
- **Method:** `GET`
- **URL Params:**
  - **Required:** `id=[integer]`
- **Success Response:**
  - **Code:** 200 OK
  - **Content:**
    ```json
    {
      "id": 1,
      "name": "John Doe"
    }
    ```
- **Error Response:**
  - **Code:** 404 Not Found
  - **Content:** `{ "error": "User not found" }`


### Insert Usuarios

- **URL:** `/backend/index.php?action=insertUsuario`
- **Method:** `POST`
- **JSON Params:**
  - **Content:**
    ```json
    {
      "ID": "1",
      "NOMBRE": "name",
      "CORREO": "email@gmail.com",
      "CLAVE": "pass123"
    }
    ```
- **Success Response:**
  - **Code:** 200 OK
  - **Content:**
    ```json
    {
      "success": true
    }
    ```
- **Error Response:**
  - **Code:** 404 Not Found
  - **Content:** `{ "error": "User not found" }`
  - **Code:** 500 Internal Server Error
  - **Content:** `{"error": "Failed to execute query -> ERR: Duplicate entry '15' for key 'USUARIO.PRIMARY' | SQL: INSERT INTO USUARIO(ID, NOMBRE, CORREO, CLAVE) VALUES (?, ?, ?, ?)"}`
