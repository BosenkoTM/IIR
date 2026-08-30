# Семинар 02. Извлечение данных из веб-документов (Web Scraping)

Семинар посвящен извлечению данных из слабоструктурированных HTML-документов как начальному этапу формирования корпуса для информационного поиска.

## Цель

Освоить разбор HTML-документов с использованием CSS-селекторов и XPath и сравнить последовательный, многопоточный и асинхронный способы получения данных.

## Материалы семинара

Основные файлы:

* `main.py` — запуск скрейпера;
* `html.ipynb` — краткое введение в структуру HTML;
* `parsers/` — парсеры на основе CSS и XPath;
* `runners/` — последовательный, многопоточный и асинхронный обход;
* `utils/` — вспомогательные компоненты.

Тестовый сайт:
https://books.toscrape.com/

## Подготовка окружения

Из корневого каталога репозитория выполните:

```bash
mkdir -p .venvs

python3 -m venv .venvs/02-scraping

source .venvs/02-scraping/bin/activate

python -m pip install --upgrade pip

python -m pip install -r seminars/02-scraping/requirements.txt
```

Проверка окружения:

```bash
python --version
python -m pip list
```

> Все зависимости рекомендуется устанавливать только в виртуальное окружение. Системная установка Python-пакетов через `sudo apt` для выполнения семинара не требуется.

## Запуск семинара

Основное задание запускается **без Jupyter**:

```bash
python seminars/02-scraping/main.py
```

Результат сохраняется в файл:

```text
result.jsonl
```

Параметры запуска задаются в `main.py`.

По умолчанию используется:

```python
seed_urls = [
    'https://books.toscrape.com/catalogue/category/books/fantasy_19/index.html'
]
```

и парсер:

```python
parser = CssSelectorParser()
```

Для проверки XPath замените его на:

```python
parser = XPathParser()
```

## Режимы обхода

В `main.py` предусмотрены три реализации:

```python
SimpleRunner
MultiThreadedRunner
AsyncRunner
```

Для выполнения семинара последовательно запустите каждый вариант и сравните время работы.

Например:

```python
runner = SimpleRunner(...)
```

```python
runner = MultiThreadedRunner(
    parser,
    sink,
    logger,
    seed_urls,
    max_parallel=5
)
```

Асинхронный вариант находится в соответствующем блоке `main.py`.

## Работа с Jupyter Notebook

Файл `html.ipynb` является дополнительным учебным материалом. Если необходимо открыть его, установите Jupyter **в активное виртуальное окружение**:

```bash
python -m pip install notebook ipykernel
```

Затем:

```bash
python -m notebook
```

или:

```bash
jupyter notebook
```

После запуска откройте:

```text
seminars/02-scraping/html.ipynb
```

## Задание

Разработайте и исследуйте программу-скрейпер для сайта `books.toscrape.com`.

Необходимо:

1. извлекать данные с помощью CSS-селекторов и XPath;
2. выполнить последовательный, многопоточный и асинхронный обход;
3. сохранить извлеченные данные в `JSONL`;
4. сравнить время выполнения трех способов обхода;
5. сделать краткий вывод о полученных результатах.

## Результат

После выполнения семинара должны быть получены:

```text
result.jsonl
```

и результаты сравнения времени выполнения:

| Режим            | Время, с |
| ---------------- | -------: |
| Последовательный |          |
| Многопоточный    |          |
| Асинхронный      |          |

В выводе кратко объясните различия между способами выполнения запросов.

## Завершение работы

После окончания работы деактивируйте окружение:

```bash
deactivate
```


## Задание
Необходимо разработать программу-скрейпер для сайта https://books.toscrape.com.
Программа должна обходить все страницы с книгами из заданного раздела (раздел задается урлом, с которого надо начинать обход).
Парсинг страниц надо осуществлять
* при помощи механизма css-селекторов;
* при помощи механизма xpath-ов.

Обход страниц с книгами сделать
* однопоточным;
* многопоточным;
* асинхронным.

## Материалы
1. Ryan Mitchell. Web scraping with python. https://library-it.com/wp-content/uploads/2020/10/web-scraping-with-python.pdf.
2. DOM. Википедия. https://en.wikipedia.org/wiki/Document_Object_Model
3. CSS и XPath для QA: чтобы разобраться с локаторами, нужно всего лишь…. https://habr.com/ru/companies/skyeng/articles/588282/.
4. Ultimate CSS Selector Cheatsheet for HTML Parsing. https://scrapfly.io/blog/css-selector-cheatsheet/.
5. The Ultimate XPath Cheat Sheet. https://bugbug.io/blog/software-testing/the-ultimate-xpath-cheat-sheet/.
6. Маппинг css-селекторов и xpath. https://devhints.io/xpath.
7. Документация Beautiful Soup. https://www.crummy.com/software/BeautifulSoup/bs4/doc/.
8. Документация lxml, раздел про xpath. https://lxml.de/xpathxslt.html.
9. Документация concurrent.futures. https://docs.python.org/3/library/concurrent.futures.html.
10. Python Asyncio: The Complete Guide. https://superfastpython.com/python-asyncio/.
11. Документация requests. https://requests.readthedocs.io/en/latest/.
12. Документация aiohttp. https://docs.aiohttp.org/en/stable/index.html.
