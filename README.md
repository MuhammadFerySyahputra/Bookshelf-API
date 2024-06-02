
# Bookshelf-API


This API is created to manage a collection of books. It allows users to add, view, update, and delete books.





## Features


- **Add a Book**
- **View All Books**
- **View Book Details**
- **Update a Book**
- **Delete a Book**
## Run Locally

Clone the project

```bash
  git clone https://github.com/MuhammadFerySyahputra/Bookshelf-API.git
```

Go to the project directory

```bash
  cd Bookshelf-API
```

Install Dependencies: Install semua dependensi yang diperlukan.

```bash
  npm install
```

Menjalankan Server

```bash
  npm run start
```


## API Routes

**1 Add a Book**
- Endpoint: /books
- Method: POST
- Body Request:
```json
{
    "name": string,
    "year": number,
    "author": string,
    "summary": string,
    "publisher": string,
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```
- Response:
    - Success: Status code 201 :

    ```json
    {
        "status": "success",
        "message": "Buku berhasil ditambahkan",
        "data": {
          "bookId": "id"
        }
    }
    ```
    - Failure: Status code 400 :

    ```json
    {
        "status": "fail",
        "message": "Gagal menambahkan buku. Mohon isi nama buku"
    }
    ```
    or
    ```json
    {
        "status": "fail",
        "message": "Gagal menambahkan buku. readPage tidak boleh lebih besar dari pageCount"
    }
    ```
**2. View All Books**
- Endpoint: /books
- Method: GET
- Response:
    - Success: Status code 200
    ```json
    {
        "status": "success",
        "data": {
            "books": [
                {
                    "id": "book_id",
                    "name": "Book A",
                    "publisher": "Dicoding Indonesia"
                }
            ]
        }
    }
    ```
    - If no books have been entered, the server can respond with an empty book array.
    ```json
    {
        "status": "success",
        "data": {
            "books": []
        }
    }
    ```
**3. View Book Details**
- Endpoint: /books/{bookId}
- Method: GET
- Response:
    - Success: Status code 200
    ```json
    {
        "status": "success",
        "data": {
            "book": {
                "id": "book_id",
                "name": "Book A",
                "year": 2021,
                "author": "John Doe",
                "summary": "Lorem ipsum",
                "publisher": "Dicoding Indonesia",
                "pageCount": 100,
                "readPage": 50,
                "finished": false,
                "reading": true,
                "insertedAt": "2021-03-04T09:11:44.598Z",
                "updatedAt": "2021-03-04T09:11:44.598Z"
            }
        }
    }
    ```
    - Failure: Status code 404 :
    ```json
    {
        "status": "fail",
        "message": "Buku tidak ditemukan"
    }
    ```
**4. Update a Book**
- Endpoint: /books/{bookId}
- Method: PUT
- Body Request:
```json
{
    "name": string,
    "year": number,
    "author": string,
    "summary": string,
    "publisher": string,
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```
- Response:
    - Success: Status code 200
    ```json
    {
        "status": "success",
        "message": "Buku berhasil diperbarui"
    }
    ```
    - Failure: Status code 400
    ```json
    {
        "status": "fail",
        "message": "Gagal memperbarui buku. Mohon isi nama buku"
    }
    ```
    - Failure: Status code 400
    ```json
    {
        "status": "fail",
        "message": "Gagal memperbarui buku. readPage tidak boleh lebih besar dari pageCount"
    }
    ```
    - Failure: Status code 404
    ```json
    {
        "status": "fail",
        "message": "Gagal memperbarui buku. Id tidak ditemukan"
    }
    ```

**5. Delete a Book**
- Endpoint: /books/{bookId}
- Method: DELETE
- Response:
     - Success: Status code 200
    ```json
    {
        "status": "success",
        "message": "Buku berhasil dihapus"
    }
    ```

    - Failure: Status code 404
    ```json
    {
        "status": "fail",
        "message": "Buku gagal dihapus. Id tidak ditemukan"
    }
    ```

## Demo

https://api.muhammadferysyahputra.my.id/books


## Authors

- This API is developed by me. If you have any questions or issues, feel free to contact me at https://t.me/ferys2343.

