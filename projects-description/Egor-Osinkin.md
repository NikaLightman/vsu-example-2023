# Осинкин Егор

## Описание предметной области

**Админка сайта с заказами**
Мобильная версия админки сайта с заказами, которая будет предоставлять возможности для просмотра каталога заказов, 
их сортировки, фильтрации, добавления, удвления и редактирования. Будет содержать в себе функциональности, связанные с валидацией добавляемых и редактируемых заказов
### Стек

`TypeScript`, `React`, `Nextjs`

---

## Описание страниц

- Страница со списком всех заказов. Каждый заказ представлен карточкой с полями:
  - Заголовок заказа
  - Заказчик
  - Описание
  - Ценник

- Страница с заказом
  - Заголовок заказа
  - Заказчик
  - Способ связи с заказчиком
  - Описание
  - Ценник
  - Требования к исполнителю

- Страница для редактирования заказа (форма с валидацией):
  - Заголовок заказа
  - Заказчик
  - Способ связи с заказчиком
  - Описание
  - Ценник
  - Требования к исполнителю
- Страница для добавления заказа, аналогично редактированию
- Страница для удаления заказа:
  - информация о заказе
  - кнопки подтвердить/удалить
- Кастомные страницы ошибок:
  - 404
  - 500

- Для навигации
  - кнопки
  - таббар

### Фильтрация

- Страница со списком всех заказов:
  - По способу связи с заказчиком
  - По заказчику
  - По ценнику

### Сортировка

- Страница со списком всех заказов:
  - По заказчику
  - По ценнику
  - По заголовку
  - По требованиям (уровню сложности)

---

## Список API

Список очень приблизительный, детально проработаю его в процессе, сейчас планируется:

---

**Эндпоинт:** `/get_oreders`

Нужен, чтобы получить список заказов, отфильтровать его в соответствии с переданными фильтрами и выполнить сортировку по соответствующему ключу

**Http метод:** `GET`

**Параметры:**

- `page: number`
- `category: Category | undefined`
- `countPerPage: number | undefined`
- `orderBy: SortingKey | undefined`
- `filters: Filters | undefined`

---

**Эндпоинт:** `/update_order`

Обновление полей уже существующего заказа

**Http метод:** `PATCH`

**Параметры:**
- `id`: number
- `title`: string (название заказа)
- `description`: string (описание)
- `salary`: number (ценник)
- `customer`: string (заказчик)
- `method_communic`: string (способ связи)
- `requitement`: string (требования)

---

**Эндпоинт:** `/remove_order`

Удаление заказа по id 

**Http метод:** `DELETE`

**Параметры:**

- `id: number`

---

**Эндпоинт:** `/add_order`

Добавление нового продукта

**Http метод:** `POST`

**Параметры:**
- `id`: number
- `title`: string (название заказа)
- `description`: string (описание)
- `salary`: number (ценник)
- `customer`: string (заказчик)
- `method_communic`: string (способ связи)
- `requitement`: string (требования)

---

**Эндпоинт:** `/get_order`

получение заказа по id

**Http метод:** `GET`

**Параметры:**

- `id: number`

---