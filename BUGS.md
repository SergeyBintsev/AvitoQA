1. Сохранение объявления. Тело ответа не соответствует Swagger

Критичный!

Сценарий:
Отправить POST запрос https://qa-internship.avito.com/api/1/item
Тело запроса:
{
  "sellerID": 270296,
  "name": "Product_1",
  "price": 9999,
  "statistics": {
    "likes": 99,
    "viewCount": 999,
    "contacts": 9
  }
}

ОР:
Тело ответа:
{
  "id": "fdcf6b0e-2223-4e3b-ae4b-f70dc5e5b2c2",
  "sellerId": 270296,
  "name": "Product_1",
  "price": 9999,
  "createdAt": "2025-12-28 19:05:27.990033 +0300 +0300",
  "statistics": {
    "likes": 99,
    "viewCount": 999,
    "contacts": 9
  }
}

ФР:
Тело ответа:
{
    "status": "Сохранили объявление - fdcf6b0e-2223-4e3b-ae4b-f70dc5e5b2c2"
}


2. Общая ошибка. Для полей с integer недоступен ввод 0

Блокер!

Сценарий:

Сценарий:
Отправить POST запрос https://qa-internship.avito.com/api/1/item
Тело запроса:
{
  "sellerID": 270296,
  "name": "Product_1",
  "price": 9999,
  "statistics": {
    "likes": 0,
    "viewCount": 0,
    "contacts": 0
  }
}

ОР:
Тело ответа:
{
  "id": "fdcf6b0e-2223-4e3b-ae4b-f70dc5e5b2c2",
  "sellerId": 270296,
  "name": "Product_1",
  "price": 9999,
  "createdAt": "2025-12-28 19:05:27.990033 +0300 +0300",
  "statistics": {
    "likes": 0,
    "viewCount": 0,
    "contacts": 0
  }
}

ФР:
Тело ответа:
{
    "result": {
        "message": "поле likes обязательно",
        "messages": {}
    },
    "status": "400"
}
