# API Testing Pet Project
## Описание
Pet project для демонстрации навыков API тестирования с использованием Postman.
## Технологии
- Postman
- JavaScript (для тестов)
- REST API

## Покрытие тестирования
- CRUD операции (JSONPlaceholder)
- Query параметры (OpenWeatherMap)
- Различные HTTP статус-коды (ReqRes)
- Негативное тестирование
- Валидация структуры ответов
- Работа с переменными окружения
- Цепочки запросов (chaining)

## Статистика
- **Всего запросов**: 14
- **Автотестов**: 40+
- **API сервисов**: 3
- **Папок**: 4
## Примеры тестов

### Валидация статус-кода и времени ответа
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});
```

### Проверка структуры данных
```javascript
pm.test("Response has correct structure", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('userId');
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('title');
});
```

### Pre-request скрипт
```javascript
const randomTitle = "Test Post" + Math.floor(Math.random() * 10000);
pm.variables.set("random_title", randomTitle);
```

### Сохранение данных в переменные
```javascript
pm.test("Save created post ID", function () {
    const jsonData = pm.response.json();
    pm.environment.set("created_post_id", jsonData.id);
    console.log("Created post ID: " + jsonData.id);
});
```

## Используемые API
1. **JSONPlaceholder** - https://jsonplaceholder.typicode.com
   - Бесплатный fake REST API для тестирования
   - CRUD операции с постами, пользователями, комментариями

2. **OpenWeatherMap** - https://openweathermap.org/api
   - Погодные данные в реальном времени
   - Требует бесплатную регистрацию для получения API ключа

3. **ReqRes** - https://reqres.in
   - REST API для тестирования различных HTTP статус-кодов
   - Бесплатный fake REST API для тестирования
   - Симуляция реальных сценариев (регистрация, логин)

## Навыки, продемонстрированные в проекте

### Технические навыки:

- Создание и организация коллекций в Postman
- Написание автоматизированных тестов на JavaScript
- Работа с переменными окружения
- Валидация JSON ответов
- Тестирование всех HTTP методов (GET, POST, PUT, PATCH, DELETE)
- Работа с Query параметрами и Headers
- Pre-request скрипты для генерации динамических данных
- Цепочки запросов (request chaining)

### Тестовое покрытие:

- Позитивное тестирование (happy path)
- Негативное тестирование (400, 401, 404)
- Валидация структуры и типов данных
- Проверка производительности (response time)
- Тестирование различных статус-кодов

## Файлы в репозитории

- `API_Testing_Pet_Project.postman_collection.json` - коллекция запросов и тестов
- `API_Testing_Env.postman_environment.json` - переменные окружения
- `README.md` - документация проекта

## Контакты

[Malika Bobokalonova]  
Email: bobokalonovamalika17@gmail.com  
LinkedIn: [https://www.linkedin.com/in/malika-bobokalonova-9a115a387]
GitHub: [https://github.com/bobokalonovamalika17-boop]