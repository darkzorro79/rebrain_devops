# rebrain_devops
##dz1
Ваша задача — полностью развернуть все компоненты нашего TODO-приложения:

    Установите базу данных postgresql и создайте пользователя для доступа приложения back.
    Запустите приложение back на порту 8080.
    Соберите frontend-приложение с помощью npm run build.
    Установите зависимости и запустите cleaner.py воркера.
    Установите и настройте nginx таким образом, чтобы запросы к /api отправлялись на приложение back, а при запросах на / отображалось front-приложение.

Проверка будет создавать и удалять задачи через api, а также проверять, что frontend-приложение отдаётся при запросах на /.
