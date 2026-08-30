# Лабораторная работа № 3  
## Машинное обучение ранжированию

**Цель:** освоить постановку Learning-to-Rank и сравнение ML-модели с классическим ранжированием.

### Материалы

- Семинар: [Learning to Rank](https://github.com/BosenkoTM/IIR/tree/main/seminars/08-learning-to-rank)
- Исходное задание: [HW3 — Learning to Rank](https://github.com/BosenkoTM/IIR/tree/main/homeworks/hw3-learning-to-rank)

### Инструменты

Python 3.12, Jupyter Notebook, CatBoost / LightGBM / XGBoost, pandas.

## Ход работы

1. Изучите структуру набора MSLR и признаки пары `query-document`.
2. Обучите базовую модель ранжирования по материалам семинара.
3. Оцените результат по `NDCG@k` и сравните его с базовым ранжированием.
4. Выполните индивидуальный вариант: используйте заданную библиотеку, подход и `random_state`.
5. Зафиксируйте параметры модели и сделайте краткий вывод.

## Индивидуальные варианты

| Вариант | random_state | Библиотека | Подход | `NDCG@k` |
|---:|---:|---|---|---:|
| 1 | 201 | CatBoost | pointwise | 5 |
| 2 | 202 | LightGBM | pointwise | 5 |
| 3 | 203 | XGBoost | pointwise | 5 |
| 4 | 204 | CatBoost | pairwise | 5 |
| 5 | 205 | LightGBM | pairwise | 5 |
| 6 | 206 | XGBoost | pairwise | 5 |
| 7 | 207 | CatBoost | pointwise | 10 |
| 8 | 208 | LightGBM | pointwise | 10 |
| 9 | 209 | XGBoost | pointwise | 10 |
| 10 | 210 | CatBoost | pairwise | 10 |
| 11 | 211 | LightGBM | pairwise | 10 |
| 12 | 212 | XGBoost | pairwise | 10 |
| 13 | 213 | CatBoost | pointwise | 5 |
| 14 | 214 | LightGBM | pointwise | 5 |
| 15 | 215 | XGBoost | pointwise | 5 |
| 16 | 216 | CatBoost | pairwise | 5 |
| 17 | 217 | LightGBM | pairwise | 5 |
| 18 | 218 | XGBoost | pairwise | 5 |
| 19 | 219 | CatBoost | pointwise | 10 |
| 20 | 220 | LightGBM | pointwise | 10 |
| 21 | 221 | XGBoost | pointwise | 10 |
| 22 | 222 | CatBoost | pairwise | 10 |
| 23 | 223 | LightGBM | pairwise | 10 |
| 24 | 224 | XGBoost | pairwise | 10 |
| 25 | 225 | CatBoost | pointwise | 5 |

## Критерии оценки

| Критерий | Баллы |
|---|---:|
| Подготовка данных для Learning-to-Rank | 5 |
| Обучение и воспроизводимость модели | 6 |
| NDCG и сравнение с базовым методом | 5 |
| GitHub-оформление и вывод | 4 |
| **Итого** | **20** |

## Оформление и сдача

Работа размещается в GitHub-репозитории или отдельной ветке. Рекомендуемая структура:

```text
lab_03/
├── README.md
├── lab_03.ipynb
├── solution.py          # при необходимости
└── requirements.txt
```

В `README.md` указываются ФИО, группа, номер варианта, краткое описание метода, полученный результат и вывод. Код должен воспроизводиться после установки зависимостей из `requirements.txt`.

## Дополнительная самостоятельная работа

По желанию выполните аналог одного из этапов поиска средствами PostgreSQL и кратко сравните результат с Python-реализацией. Дополнительная часть может повысить оценку на **1 балл**, но итог за лабораторную работу не превышает **20 баллов**.
