# Booky Backend Service

Booky is a simple backend service built with Go, Gorm, and SQLite, providing an API for sharing and borrowing books.

## Project Structure
```
.
├── controllers/
│   └── book_controller.go
├── types/
│   ├── book.go
│   └── borrow.go
└── main.go
```

## API Endpoints

- Add a Book for Sharing
    ```http
    POST /api/v1/booky/

    {
        "name": "The Book Title"
    }
    ```

- Browse Books
    ```http
    GET /api/v1/booky/
    ```
- List Borrows
    ```http
    GET /api/v1/borrow/
    ```
- Borrow a Book
    ```http
    POST /api/v1/booky/{book_id}/borrow

    {
        "borrow_start_time": "2023-01-01T10:00:00Z",
        "borrow_end_time": "2023-01-10T18:00:00Z"
    }
    ```
- Return a Borrowed Book
    ```http
    PUT /api/v1/booky/{book_id}/borrow/{borrow_id}
    ```

## Setup
### Install Go dependencies:

```bash
go get -u gorm.io/gorm
go get -u gorm.io/driver/sqlite
go get -u github.com/gin-gonic/gin
```
### Run the application:

```bash
go run main.go
```
By default, the server will be running on http://localhost:8000.

### Author
[probablyarth](https://github.com/probablyarth)

### License
This project is licensed under the MIT License - see the LICENSE file for details.
