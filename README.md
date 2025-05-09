## Проект на автомат за экзамены по двум дисциплинам
### Александр Силицкий, ГБПОУ "Колледж связи №54" им. П.М. Вострухина, группа 1АСС11-8, отделение ОП-6 АСТ
Бот развёртывается посредством включения контейнера Docker на VPS-сервер и его установки через SSH. Для хранения секретов вместо .env-файла реализованы переменные среды в GitHub Actions. Небезопасное хранение токена в самом репозитории обусловлено самим пайплайном процесса развёртывания приложения, в ходе которого контейнеризованное приложение вытягивает токен из конфигурационного INI-файла. Также реализована возможность одновременного подъёма бота и базы через Docker Compose (`compose.yaml`). Бот асинхронный, написан на Python 3.13, в качестве БД используется PostgreSQL. Планируется реализация считывания запроса для автоинициализации БД из файла.

# Бот Telegram для управления задачами

Функциональные возможности:

- Просмотр задач
- Создание задач
- Удаление задач
- Редактирование задач

## Стек

- База данных - PostgreSQL
- Возможность оркестрации с Docker Compose

## Требования

- Docker и Docker Compose (желательно с бэкендом WSL2)
- Токен для бота Telegram

## Установка

1. Клонировать репозиторий
    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```

2. Установить пакеты
    ```pip install -r requirements.txt```

3. Редактировать INI-файл
    ```[database]
    user = postgres
    password = Passlogin1.
    host = db
    dbname = project
    port = 5432
    ```

4. Адаптировать файл `compose.yaml` под ваши требования

5. Запустить приложение через Docker Compose
    ```bash
    docker-compose up --build
    ```

## Структура проекта

- `./` - Исходный код бота
- `./config.ini` - Конфигурационный файл бота
- `./compose.yaml` - Конфигурационный файл Docker Compose
