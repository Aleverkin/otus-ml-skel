# Правила работы с кодом

## Настройка окружения

### Создание virtualenv
Чтобы точно воспроизвести окружение и версии библиотек необходимо использовать virtualenv
```
python3 -m venv venv
```

Будет создана директория venv, из которой можно активировать окружение

Для Linux и MacOs
```
source venv/bin/activate
```

Для Windows
```
venv\Scripts\activate.bat
```

### Установка зависимостей
Сперва рекомендуется обновить pip
```
pip install --upgrade pip
```

Для установки зависимстей необходимо активировать окружение и выполнить
```
pip install -r requirements.txt
```

### Установка основного пакета

Для переиспользования кода из пакета titanic нужно установить его в режиме редактирования
```
pip install -e .
```

## Запуск jupyter notebook

Запускать jupyter-notebook следует из виртуального окружения. Тогда будут доступны все зависимости
Пример можно посмотреть в notebooks/EDA.ipynb

## Внесение изменений в код

Все изменения должны быть привязаны к issue на github.

Шаблон имени ветки - feature/<#issue>-<description>

Все изменение в main ветку проводятся через создание Pull Requests из feature веток.

## Требования к новому коду

Для форматирования кода использовать black
```
black src tests
```

Для статического анализа использовать mypy
```
mypy src
```

и pylint
```
pylint src
```

## Запуск тестов

Для запуска тестов используется pytest c модулем pytest-cov для оценки покрытия кода
```
pytest --cov=src tests
```