# Отчёт о тестировании REST API JSONPlaceholder

**Дата:** 22.07.2026  
**Тестируемая версия:** актуальная на момент прогона (https://jsonplaceholder.typicode.com)  
**Окружение:** Postman v12.20.0

---

## Результаты прогона коллекции

| Показатель         | Значение |
|--------------------|----------|
| Всего тест-кейсов  | 37       |
| Пройдено           | 37       |
| Провалено          | 0        |
| Заблокировано      | 0        |

Все запросы выполнились успешно, ожидаемые статус-коды и структуры ответов соответствуют документации.

---

## Ссылка на коллекцию Postman и Environments

[Коллекция в Postman Workspace](https://www.postman.com/ivansaltuganov/educational/collection/46402563-5f3815f7-6b45-469a-a642-aa73d9c89742?action=share&source=copy-link&creator=46402563)
[Переменные окружения в Postman Workspace](https://www.postman.com/ivansaltuganov/educational/environment/46402563-0f041946-a078-4a99-a567-e31e1a72d8f1?action=share&source=copy-link&creator=46402563)

---

## Скриншот прогона коллекции (Collection Runner)

![Collection Run Summary - 1](.collection_run_1.png)

![Collection Run Summary - 2](.collection_run_1.png)


---

## Примечания

- **Особенности тестируемого API:** JSONPlaceholder является мок-сервером. Методы POST, PUT, PATCH и DELETE не вносят реальных изменений на сервере, но возвращают ожидаемые коды и тела ответов (имитация успешной операции). Это учтено в тест-кейсах и проверках.
- **Автоматические проверки:** Каждый запрос содержит скрипты во вкладке Tests, которые проверяют:
  - Код состояния HTTP.
  - Тип и структуру тела ответа.
  - Соответствие значений полей (например, `userId`, `postId`, количество элементов).
- **Покрытие:** Тесты охватывают все 6 ресурсов (`/posts`, `/comments`, `/albums`, `/photos`, `/todos`, `/users`) и основные HTTP-методы: GET (одиночный/список/фильтрация/вложенные маршруты), POST, PUT, PATCH, DELETE. Также включены негативные сценарии (несуществующие ID).
