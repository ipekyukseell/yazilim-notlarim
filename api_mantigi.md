# 8) API Mantığı (REST & JSON Temelleri)

## 1. API Mantığı Nedir?

**API (Application Programming Interface)**, farklı yazılımların birbiriyle iletişim kurmasını sağlayan bir arayüzdür.

Bir uygulamanın başka bir uygulamadan veri almasını, veri göndermesini veya belirli bir işlemi gerçekleştirmesini sağlar.

Örneğin bir mobil uygulamada kullanıcı bilgilerini göstermek istediğimizi düşünelim:

```text
Mobil Uygulama
      ↓
     API
      ↓
   Backend
      ↓
  Veritabanı
```

Mobil uygulama doğrudan veritabanına bağlanmak yerine API üzerinden backend'e istek gönderir.

Backend gerekli işlemi yaptıktan sonra sonucu API üzerinden uygulamaya gönderir.

### API Neden Kullanılır?

API sayesinde:

- Frontend ve backend arasında iletişim sağlanır.
- Uygulamalar arasında veri alışverişi yapılır.
- Mobil ve web uygulamaları aynı backend'i kullanabilir.
- Veritabanına erişim kontrollü bir şekilde sağlanabilir.
- Farklı servislerin birbiriyle iletişim kurması sağlanabilir.

### Basit Bir Örnek

Bir alışveriş uygulamasında ürünleri görüntülemek istediğimizi düşünelim.

```text
Frontend
   ↓
GET /products
   ↓
API
   ↓
Backend
   ↓
Database
```

Backend ürünleri veritabanından alır ve API üzerinden frontend'e gönderir.

Kısaca:

> **API, farklı uygulamaların birbiriyle iletişim kurmasını sağlayan bir köprü görevi görür.**

---

# 2. GET – POST – PUT – DELETE Nedir?

REST API'lerde veriler üzerinde işlem yapmak için **HTTP metotları** kullanılır.

En sık kullanılan dört temel HTTP metodu:

- **GET**
- **POST**
- **PUT**
- **DELETE**

Bunları bir öğrenci sistemi üzerinden düşünebiliriz.

---

## GET

**GET**, sunucudan veri almak veya mevcut verileri okumak için kullanılır.

Örneğin bütün öğrencileri almak için:

```http
GET /students
```

Bu istek sonucunda backend öğrenci listesini döndürebilir.

Örnek cevap:

```json
[
    {
        "id": 1,
        "name": "İpek"
    },
    {
        "id": 2,
        "name": "Ayşe"
    }
]
```

### GET'in amacı

```text
GET → Veri getir / oku
```

Örneğin:

- Öğrencileri getir
- Kullanıcıları getir
- Ürünleri getir
- Siparişleri getir

gibi işlemlerde kullanılır.

---

## POST

**POST**, sunucuya yeni veri göndermek ve genellikle yeni bir kaynak oluşturmak için kullanılır.

Örneğin sisteme yeni öğrenci eklemek için:

```http
POST /students
```

Gönderilen veri:

```json
{
    "name": "İpek",
    "department": "Computer Engineering"
}
```

Backend bu bilgileri alarak yeni bir öğrenci oluşturabilir.

### POST'un amacı

```text
POST → Yeni veri oluştur
```

Örneğin:

- Yeni kullanıcı oluştur
- Yeni ürün ekle
- Yeni öğrenci oluştur
- Yeni sipariş oluştur

gibi işlemlerde kullanılır.

---

## PUT

**PUT**, mevcut bir kaynağı güncellemek için kullanılır.

Örneğin ID'si `5` olan öğrenciyi güncellemek:

```http
PUT /students/5
```

Gönderilen veri:

```json
{
    "name": "İpek Yüksel",
    "department": "Computer Engineering"
}
```

Backend bu bilgileri kullanarak `5` numaralı öğrencinin bilgilerini güncelleyebilir.

### PUT'un amacı

```text
PUT → Mevcut veriyi güncelle
```

Örneğin:

- Kullanıcı bilgilerini güncelle
- Ürün bilgilerini güncelle
- Öğrenci bilgilerini güncelle

gibi işlemlerde kullanılır.

---

## DELETE

**DELETE**, mevcut bir kaynağı silmek için kullanılır.

Örneğin ID'si `5` olan öğrenciyi silmek:

```http
DELETE /students/5
```

Backend bu isteği alır ve ilgili öğrenciyi silebilir.

### DELETE'in amacı

```text
DELETE → Veriyi sil
```

Örneğin:

- Kullanıcı sil
- Ürün sil
- Öğrenci sil
- Sipariş sil

gibi işlemlerde kullanılabilir.

---

## HTTP Metotlarının Kısa Özeti

| HTTP Method | Görevi |
|---|---|
| `GET` | Veri getir / oku |
| `POST` | Yeni veri oluştur |
| `PUT` | Mevcut veriyi güncelle |
| `DELETE` | Veri sil |

Kısaca:

```text
GET     → Oku
POST    → Oluştur
PUT     → Güncelle
DELETE  → Sil
```

---

# 3. JSON Yapısı Nedir?

**JSON (JavaScript Object Notation)**, uygulamalar arasında veri alışverişinde kullanılan bir veri formatıdır.

API'lerde verilerin gönderilmesi ve alınması sırasında JSON çok sık kullanılır.

JSON insanlar tarafından kolay okunabilir ve programlar tarafından kolay işlenebilir.

## Basit JSON Örneği

```json
{
    "name": "İpek",
    "age": 21,
    "student": true
}
```

JSON yapısında bilgiler genellikle **key-value (anahtar-değer)** şeklinde tutulur.

Örneğin:

```text
"name" → "İpek"

"age" → 21

"student" → true
```

Burada:

- `name` → key
- `"İpek"` → value
- `age` → key
- `21` → value
- `student` → key
- `true` → value

şeklindedir.

---

## JSON Veri Tipleri

### String

Metinsel verileri ifade eder.

```json
{
    "name": "İpek"
}
```

### Number

Sayısal verileri ifade eder.

```json
{
    "age": 21
}
```

### Boolean

`true` veya `false` değerlerini ifade eder.

```json
{
    "student": true
}
```

### Array

Birden fazla değeri liste halinde tutar.

```json
{
    "languages": [
        "Python",
        "C++",
        "JavaScript"
    ]
}
```

### Object

Bir JSON nesnesinin içerisinde başka bir nesne bulunabilir.

```json
{
    "student": {
        "name": "İpek",
        "age": 21
    }
}
```

---

## API'de JSON Kullanımı

Frontend backend'e bir istek gönderdiğinde JSON veri gönderebilir.

Örneğin:

```http
POST /students
```

Gönderilen JSON:

```json
{
    "name": "İpek",
    "age": 21,
    "department": "Computer Engineering"
}
```

Backend bu veriyi alır, işler ve gerektiğinde yine JSON formatında cevap döndürür.

Örneğin backend şu şekilde cevap verebilir:

```json
{
    "id": 5,
    "name": "İpek",
    "age": 21,
    "department": "Computer Engineering"
}
```

Bu nedenle:

> **JSON, API üzerinden frontend ve backend arasında veri alışverişi yapmak için kullanılan yaygın bir veri formatıdır.**

---

# 4. Basit Bir Endpoint Nasıl Tasarlanır?

**Endpoint**, API içerisinde belirli bir kaynağa veya işleme erişmek için kullanılan URL yoludur.

Örneğin bir öğrenci sistemi geliştirdiğimizi düşünelim.

Öğrenciler için temel endpoint:

```text
/students
```

Belirli bir öğrenciye ulaşmak için:

```text
/students/5
```

kullanılabilir.

Buradaki `5`, öğrencinin ID değeridir.

---

## Öğrenci API'si Tasarlayalım

Bir öğrenci sistemi için endpoint'leri şu şekilde oluşturabiliriz:

```text
GET     /students
POST    /students
GET     /students/5
PUT     /students/5
DELETE  /students/5
```

Bunların görevleri:

### Tüm öğrencileri getir

```http
GET /students
```

Bu endpoint bütün öğrencileri getirir.

---

### Yeni öğrenci oluştur

```http
POST /students
```

Bu endpoint yeni öğrenci oluşturmak için kullanılır.

Gönderilecek JSON:

```json
{
    "name": "İpek",
    "age": 21,
    "department": "Computer Engineering"
}
```

Backend bu bilgileri alarak yeni öğrenciyi veritabanına kaydedebilir.

---

### Belirli öğrenciyi getir

```http
GET /students/5
```

Bu endpoint ID'si `5` olan öğrenciyi getirir.

Örnek cevap:

```json
{
    "id": 5,
    "name": "İpek",
    "age": 21,
    "department": "Computer Engineering"
}
```

---

### Öğrenciyi güncelle

```http
PUT /students/5
```

Bu endpoint ID'si `5` olan öğrencinin bilgilerini güncellemek için kullanılır.

Örneğin:

```json
{
    "name": "İpek Yüksel",
    "age": 22,
    "department": "Computer Engineering"
}
```

---

### Öğrenciyi sil

```http
DELETE /students/5
```

Bu endpoint ID'si `5` olan öğrenciyi silmek için kullanılır.

---

## Endpoint Tasarım Mantığı

Endpoint tasarlarken kaynakların isimlerini açık ve anlaşılır tutmak önemlidir.

Örneğin:

```text
/students
/users
/products
/orders
```

gibi isimler kullanılabilir.

HTTP metodu yapılacak işlemi belirlediği için endpoint'in içerisine genellikle işlemi belirten fiiller eklenmez.

Örneğin:

```text
GET /students
```

kullanmak,

```text
GET /getStudents
```

kullanmaktan daha uygun bir REST yaklaşımıdır.

Çünkü `GET` zaten verinin alınacağını belirtmektedir.

Bu nedenle:

```text
GET /students
→ Öğrencileri getir

POST /students
→ Yeni öğrenci oluştur

PUT /students/5
→ 5 numaralı öğrenciyi güncelle

DELETE /students/5
→ 5 numaralı öğrenciyi sil
```

şeklinde düşünülebilir.

---

# Genel Özet

Bu konuda dört temel kavram öğrenildi:

### API

Farklı uygulamaların birbiriyle iletişim kurmasını sağlayan arayüzdür.

### GET – POST – PUT – DELETE

```text
GET     → Veri getir
POST    → Yeni veri oluştur
PUT     → Veriyi güncelle
DELETE  → Veriyi sil
```

### JSON

API üzerinden veri alışverişinde kullanılan veri formatıdır.

Örneğin:

```json
{
    "name": "İpek",
    "age": 21
}
```

### Endpoint

API içerisinde belirli bir kaynağa erişmek için kullanılan URL yoludur.

Örneğin:

```text
GET /students
GET /students/5
POST /students
PUT /students/5
DELETE /students/5
```

---

## Kazanım

> **API, REST, HTTP metotları, JSON ve endpoint mantığını öğrenerek backend uygulamalarının frontend ile nasıl iletişim kurduğunu anlamış oldum.**