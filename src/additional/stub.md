# Stub файлы и работа с нетипизированными библиотеками

Важно понимать, что type hinting работает не только для аргументов функций и возвращаемых значений. Мы можем просто создать переменную и указать ей тип:

```python
book: str = "Тополек мой в красной косынке"
```

В таком сценарии это избыточно — IDE и статический анализатор кода и так видят, что в переменной `book` хранится значение типа `str`. Однако в таком сценарии:

```python
book: str = find_book_in_library("Тополек мой в красной косынке")
```

функция поиска книги `find_book_in_library` может быть не нашей функцией, а функцией какой-то внешней библиотеки, которая не использует подсказки типов. То есть для функции может быть не проставлен тип возвращаемого значения. Чтобы IDE и статический анализатор знали, что тип данных, который будет храниться в `book`, это именно `str`, можно таким образом подсказать инструментам о верном типе. Иногда это бывает очень полезно, когда библиотека не использует подсказки типов, а возвращаемый тип данных какой-то сложный и мы хотим, чтобы IDE и mypy нам помогали анализировать наш код и типы.

В то же время в Python существует механизм так называемых стаб-файлов, которые позволяют типизировать в том числе внешние библиотеки. Например, для django есть пакет в pip, который называется `django-stubs`. О стаб-файлах есть [видео](https://www.youtube.com/watch?v=KofihAoSp2U) на канале Диджитализируй!.

Если вы используете нетипизированную библиотеку — можно поискать готовые стаб файлы для неё, чтобы воспользоваться преимуществами типизированного Python.