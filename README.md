# Парсинг бесплатной библиотеки https://tululu.org/ по жанрам.

Программа позволяет получить данные из библиотеки о книге:
* Название
* Автор
* Жанр книги
* Комментарии пользователей сайта

Также можно скачать текст книги и обложку книги.

Вся информация о загруженных книгах сохраняется в файле `json`.

# Как установить

Загрузите код с репозитория.

Python3 должен быть уже установлен. 
Затем используйте pip (или pip3, если есть конфликт с Python2) для установки зависимостей:

```Python
pip install -r requirements.txt
```

## Пример запуска

```Python
python parse_tululu_category.py
``` 
Запуск без параметров скачает все книги жанра "Научная фантастика" в текущий каталог.  
Тексты книг в подкаталог `books`, обложки книг в подкаталог `images`.

Если на странице книги нет возможности скачать текст книги, то выведется предупреждение.

### Параметры командной строки
Для удобства рекомендуется использовать следующие параметры:
* `--category_page` (str). Указать ссылку на нужную категорию (например, 'https://tululu.org/l55/')

```python
python parse_tululu_category.py --category_page https://tululu.org/l55/
```

* `--start_page` (int). Стартовая страница раздела жанра для загрузки. По умолчанию - 1.
* `--end_page` (int). Конечная страница раздела жанра для загрузки. Если не указана, то будут скачиваться
все страницы жанра до конца.

```python
python parse_tululu_category.py --start_page 700
python parse_tululu_category.py --start_page 700 --end_page 701

```
* `--dest_folder` (str). Каталог для загрузки, если отличается от текущего.
* `--path_json` (str). Название файла для выгрузки результата. По умолчанию: `books.json`.
* `--skip_img`. Указать параметр, чтобы не загружать обложки книг.
* `--skip_txt`. Указать параметр, чтобы не загружать тексты книг.


## Цели проекта

Код написан в учебных целях — это урок в курсе по Python и веб-разработке на сайте [Devman](https://dvmn.org).
