# Notes App

Project aplikasi catatan sederhana yang dibangun dengan RESTful API menggunakan Hapi Framework dalam Kelas Belajar Membuat Aplikasi Back-End untuk Pemula dari Dicoding.

## Create Note

Membuat catatan yang akan disimpan pada memory server dalam bentuk array JavaScript.

** HTTP Request **

```
POST /notes
```

** Request Body **
```
{
  "title": "Judul Catatan",
  "tags": ["Tag 1", "Tag 2"],
  "body": "Konten"
}
```

** Response **

HTTP/1.1 201 Created
```
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "noteId": "V09YExygSUYogwWJ"
  }
}
```

** Error Response **

HTTP/1.1 500 Internal Server Error
```
{
  "status": "error",
  "message": "Catatan gagal untuk ditambahkan",
}
```