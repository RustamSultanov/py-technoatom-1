# Домашнее задание к лекции №5

В домашнем задании к лекции №3 мы описали класс реализующий сущность **Task** (Задача). Необходимо разработать представление и формы создания и редактирования для этой сущности. В случае успеха или неудачи заполнения форм нужно выводить соответствующие сообщения.

В домашнем задании к лекции №4 мы определили понятие "критичная задача" (критичными считаются просроченные задачи и задачи, до окончания срока которых осталось менее трех дней). В случае успеха заполнения формы необходимо вывести пользователю все поля сущности, если задача является критичной - необходимо веделить ее заголовок красным цветом.

Для решения поставленных задач необходимо применять фреймворк Django и его возможности (маршруты, представления, формы и валидацию форм, стандартные шаблоны).

### Форма создания

Форма создания должна содержать элементы:
-   поле **title** (Заголовок) типа str (строка)
-   поле **estimate** (Срок выполнения) типа datetime.date (дата)
-   кнопка "Сохранить", активирующая отправку формы на сервер

Поля формы создания имеют ограничения:
-   значение поля **estimate** (Срок выполнения) должно быть больше или равна сегодняшнему дню (date.today)
-   значения всех полей должны иметь соответствующий тип

### Форма редактирования

Форма редактирования должна содержать элементы:
-   поле **title** (Заголовок) типа str (строка)
-   поле **state** (Статус выполнения) типа str (строка):
    -   возможные значения - **in_progress** (выполняется) и **ready** (выполнена)
-   поле **estimate** (Срок выполнения) типа datetime.date (дата)
-   кнопка "Сохранить", активирующая отправку формы на сервер

Поля формы создания имеют ограничения:
-   значение поля **state** (Статус выполнения) должно быть одним из возможных значений

## Полезные ссылки

1.  [Машруты, URL dispatcher](https://docs.djangoproject.com/en/1.10/topics/http/urls/)
2.  [Представления, Views](https://docs.djangoproject.com/en/1.10/topics/http/views/)
3.  [Декораторы представлений, View decorators](https://docs.djangoproject.com/en/1.10/topics/http/decorators/)
4.  [Функции представлений, Shortcut functions](https://docs.djangoproject.com/en/1.10/topics/http/shortcuts/)
5.  [Формы, Forms](https://docs.djangoproject.com/en/1.10/topics/forms/)
6.  [Поля форм, Form fields](https://docs.djangoproject.com/en/1.10/ref/forms/fields/)
7.  [Валидация форм, Form validations](https://docs.djangoproject.com/en/1.10/ref/forms/validation/)

# Домашнее задание к лекции №6

В домашнем задании к лекции №3 мы описали классы реализующие сущности **Task** (Задача) и **Roadmap** (Дорожная карта). Необходимо описать Django-модели **Task** и **Roadmap**, с учетом того, что **Roadmap** относится к **Task** как один-ко-многим. Необходимо реорганизовать структуру маршрутов и представления для работы с моделями.

В домашнем задании к лекции №5 мы описали формы для сущности **Task** (Задача), необходимо их обновить с учетом последних изменений (используя Django Model Forms) и также реализовать формы для сущности **Roadmap** (Дорожная карта).

### Представления

1.  Представление **Список дорожных карт**, содержащее:
    -   Список записей **Roadmap** (Дорожная карта), где каждая запись сопровождается:
        -   ссылкой на просмотр задач дорожной карты
        -   ссылкой на удаление дорожной карты и всех ее задач
    -   Ссылку на создание новой записи **Roadmap** (Дорожная карта)
2.  Представление **Список задач**, содержащее:
    -   Список записей **Task** (Задача), отсортированных по статусу и срокам выполнения, где каждая запись сопровождается:
        -   полями задачи **title** (Заголовок), **state** (Статус выполнения) и **estimate** (Срок выполнения)
        -   ссылкой на изменение задачи
        -   ссылкой на удаление задачи
3.  Представление **Создание дорожно карты**
4.  Представление **Удаление дорожной карты и всех ее задач**
5.  Представление **Создание задачи**
6.  Представление **Изменение задачи**
7.  Представление **Удаление задачи**

### Маршруты

Каждая сущность должна быть определена собственным уникальным URL, для реализации этого требования использовать возможности задания параметров для маршрутов.

## Полезные ссылки

1.  [Машруты, URL dispatcher](https://docs.djangoproject.com/en/1.10/topics/http/urls/)
2.  [Подключение СУБД, Install database](https://docs.djangoproject.com/en/1.10/topics/install/#get-your-database-running)
3.  [Модели, Models](https://docs.djangoproject.com/en/1.10/topics/db/models/)
4.  [Формы моделй, Model Forms](https://docs.djangoproject.com/en/1.10/topics/forms/modelforms/)
