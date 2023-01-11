# Notes App

Project aplikasi catatan sederhana yang dibangun dengan RESTful API menggunakan Hapi Framework dalam Kelas Belajar Membuat Aplikasi Back-End untuk Pemula dari Dicoding.

## Create Note

Membuat catatan yang akan disimpan pada memory server dalam bentuk array JavaScript.

**HTTP Request**

`POST`  `/notes`

**Request Body**
```json
{
  "title": "Judul Catatan",
  "tags": ["Tag 1", "Tag 2"],
  "body": "Konten"
}
```

**Response**

HTTP/1.1 201 Created
```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "noteId": "V09YExygSUYogwWJ"
  }
}
```

**Error Response**

HTTP/1.1 500 Internal Server Error
```json
{
  "status": "error",
  "message": "Catatan gagal untuk ditambahkan",
}
```

## Get All Notes

Menampilkan semua catatan yang tersimpan.

**HTTP Request**

`GET`  `/notes`

**Response**

HTTP/1.1 200 OK
```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "notes": [
      {
        "id": "V09YExygSUYogwWJ",
        "title": "Judul Catatan",
        "createdAt": "2020-12-23T23:00:00.686Z",
        "updatedAt": "2020-12-23T23:00:00.686Z",
        "tags": [
          "Tag 1",
          "Tag 2"
        ],
        "body": "Konten"
      },
      {
        "id": "V09YExygSUYogwYZ",
        "title": "Judul Catatan",
        "createdAt": "2020-12-23T23:00:00.686Z",
        "updatedAt": "2020-12-23T23:00:00.686Z",
        "tags": [
          "Tag 1",
          "Tag 2"
        ],
        "body": "Konten"
      },
    ]
  }
}
```

## Get A Spesific Note

Menampilkan catatan.

**HTTP Request**

`GET`  `/notes/{id}`

**Response**

HTTP/1.1 200 OK
```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "note": {
      "id": "V09YExygSUYogwWJ",
      "title": "Judul Catatan",
      "createdAt": "2020-12-23T23:00:00.686Z",
      "updatedAt": "2020-12-23T23:00:00.686Z",
      "tags": [
        "Tag 1",
        "Tag 2"
      ],
      "body": "Konten"
    },
     
  }
}
```

**Error Response**

HTTP/1.1 404 Not Found
```json
{
  "status": "fail",
  "message": "Catatan tidak ditemukan",
}
```