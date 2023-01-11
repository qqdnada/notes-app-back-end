# Notes App

Project aplikasi catatan sederhana yang dibangun dengan RESTful API menggunakan Hapi Framework dalam Kelas Belajar Membuat Aplikasi Back-End untuk Pemula dari Dicoding.

Pengujian Notes API dapat menggunakan berkas Postman Collection dan Environment pada direktori [NotesAPITestCollectionAndEnvironment](./NotesAPITestCollectionAndEnvironment) yang tersedia pada branch api-docs ini.

## Create Note

Membuat catatan yang akan disimpan pada memory server dalam bentuk array JavaScript.

**HTTP Request**  `POST`  `/notes`

**Request Body**
```json
{
  "title": "Judul Catatan",
  "tags": ["Tag 1", "Tag 2"],
  "body": "Konten"
}
```

**Response**

<details>
  <summary>HTTP/1.1 201 Created</summary>

```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "noteId": "V09YExygSUYogwWJ"
  }
}
```

</details>

**Error Response**

<details>
  <summary>HTTP/1.1 500 Internal Server Error</summary>
  
```json
{
  "status": "error",
  "message": "Catatan gagal untuk ditambahkan"
}
```
</details>

## Get All Notes

Menampilkan semua catatan yang tersimpan.

**HTTP Request**  `GET`  `/notes`

**Response**

<details>
  <summary>HTTP/1.1 200 OK</summary>

```json
{
  "status": "success",
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
      }
    ]
  }
}
```
</details>

<details>
  <summary>HTTP/1.1 200 OK</summary>
  
```json
{
  "status": "success",
  "data": {
    "notes": []
  }
}
```
</details>

## Get A Spesific Note

**HTTP Request**  `GET`  `/notes/{id}`

**URL Parameter**

|Parameter  | Description                      |
|-----------|----------------------------------|
|id         | The `id` of the note to retrieve |

**Response**

<details>
  <summary>HTTP/1.1 200 OK</summary>
  
```json
{
  "status": "success",
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
    }
  }
}
```
</details>

**Error Response**

<details>
  <summary>HTTP/1.1 404 Not Found</summary>
  
```json
{
  "status": "fail",
  "message": "Catatan tidak ditemukan"
}
```
</details>

## Update Note

**HTTP Request**  `PUT` `/notes/{id}`

**URL Parameter**

|Parameter  | Description                    |
|-----------|--------------------------------|
|id         | The `id` of the note to update |


**Request Body**
```json
{
  "title": "Judul Catatan",
  "tags": ["Tag 1", "Tag 2"],
  "body": "Konten"
}
```

**Response**

<details>
  <summary>HTTP/1.1 200 OK</summary>
  
```json
{
  "status": "success",
  "message": "Catatan berhasil diperbarui"
}
```
</details>

**Error Response**

<details>
  <summary>HTTP/1.1 404 Not Found</summary>
  
```json
{
  "status": "fail",
  "message": "Gagal memperbarui catatan. Id catatan tidak ditemukan"
}
```
</details>

## Delete Note

**HTTP Request**  `DELETE` `/notes/{id}`

**URL Parameter**

|Parameter  | Description                    |
|-----------|--------------------------------|
|id         | The `id` of the note to delete |

**Response**

<details>
  <summary>HTTP/1.1 200 OK</summary>
  
```json
{
  "status": "success",
  "message": "Catatan berhasil dihapus"
}
```
</details>

**Error Response**

<details>
  <summary>HTTP/1.1 404 Not Found</summary>
  
```json
{
  "status": "fail",
  "message": "Catatan gagal dihapus. Id catatan tidak ditemukan"
}
```
</details>
