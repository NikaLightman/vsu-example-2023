# Олег Ерохин

## Описание предметной области

Админка интернет-магазина настольных игр.

Мобильная версия админки интернет-магазина настольных игр предоставляет возможность управления каталогом игр, включая их добавление, удаление, редактирование, а также просмотр, сортировку и фильтрацию. Будет содержать в себе функциональность, связанную с валидацией добавляемых и редактируемых игр.

### Стек

`TypeScript`, `React`, `Next.js`

---

## Описание страниц

* Главная страница — список настольных игр
* Страница конкретной игры — содержит изображение, описание и тд
* Страница редактирования описания игры:
  * Форма для редактирования с валидацией
  * Основные поля для редактирования, такие как название, описание, цена и тд
* Аналогично страница добавления новой игры
* Страница подтверждения удаления игры
* Кастомные страницы ошибок:
  * 404
  * 500

Для навигации будут использоваться кнопоки и вкладки

### Фильтрация

* Страница со списком игр
  * цена
  * жанр
  * рейтинг

### Сортировка

Для каждого параметра должна быть реализована сортировка по убыванию и возрастанию

* Страница со списком игр
  * цена
  * название
  * рейтинг

---

## Список API

Список очень приблизительный, детально проработаю его в процессе, сейчас планируется:

---

Эндпоинт: `/get-games`

Используется для получения списка настольных игр, с возможностью фильтрации и сортировки

Http метод: `GET`

Параметры:

* `page: number`
* `category: Category | undefined`
* `countPerPage: number | undefined`
* `orderBy: SortingKey | undefined`
* `filters: Filters | undefined`

---

Эндпоинт: `/update-game`

Позволяет обновить информацию о существующей игре

Http метод: `PUT`

Параметры:

* Название
* Описание
* Жанр
* Цена

---

Эндпоинт: `/remove-game`

Предназначен для удаления игры из каталога

Http метод: `DELETE`

Параметры:

* id

---

Эндпоинт: `/add-game`

Позволяет добавить новую настольную игру в каталог магазина

Http метод: `POST`

Параметры:

* Название
* Описание
* Жанр
* Цена

---

Эндпоинт: `/get-validation-schema`

Этот эндпоинт используется для получения схемы валидации форм для добавления и обновления игр

Http метод: `GET`

Параметры:

* `category: Category`

---