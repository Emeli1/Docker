# Используем официальный образ Python
FROM python:3.9

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем проект
COPY ./app /app

# Устанавливаем зависимости
RUN pip install -r /app/requirements.txt

# Устанавливаем переменную окружения для Django
ENV DJANGO_SETTINGS_MODULE=stocks_products.settings

# Выполняем миграции для создания базы данных
RUN python manage.py migrate

# Статистическая сборка для Django
RUN python manage.py collectstatic --noinput

# Запускаем сервер Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]


