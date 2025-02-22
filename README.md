# rebrain_devops
##dz1
Ваша задача — полностью развернуть все компоненты нашего TODO-приложения:

    Установите базу данных postgresql и создайте пользователя для доступа приложения back.
    Запустите приложение back на порту 8080.
    Соберите frontend-приложение с помощью npm run build.
    Установите зависимости и запустите cleaner.py воркера.
    Установите и настройте nginx таким образом, чтобы запросы к /api отправлялись на приложение back, а при запросах на / отображалось front-приложение.

Проверка будет создавать и удалять задачи через api, а также проверять, что frontend-приложение отдаётся при запросах на /.

##dz2
Ваша задача — настроить автоматический деплой TODO приложения в gitlab.

Доступ в Gitlab вы можете получить в личном кабинете, в разделе Настройки практикума.

При входе в Gitlab у вас не будет создано ни одного проекта — это нормально. Вам необходимо сделать форк (скопировать) репозитории для каждого из приложений в свой namespace. Для этого:

    Откройте проект https://rbr-devops-workshop.gitlab.yandexcloud.net/rbr-todo/back, справа сверху нажмите Fork. В следующем меню выберите свой namespace (он будет один возможной) и тип проекта Private. Всё! Теперь вы можете добавлять изменения в свой проект.
    По аналогии сделайте так для проектов front и worker.

Что нужно сделать:

    Настроить на сервере вход пользователей по ключу (back, front, worker).
    Добавить разрешения в sudoers-файл для пользователей back и worker, чтобы они могли перезапускать сервис через systemctl.
    Добавить переменные SSH_PRIVATE_KEY и APP_HOST для каждого из проектов.
    Добавить файл .gitlab-ci.yml для каждого из проектов (front, back, worker), который будет содержать как минимум стадии сборки и деплоймента (для воркера только стадию деплоя). Стадии должны называться build и deploy.
    Проверить, что все стадии проходят и приложение успешно обновляется на сервере.
    На сервере склонировать ваши репозитории с файлом .gitlab-ci.yml в директорию /opt/repos/:

    /opt/repos/back — для back приложения;
    /opt/repos/front — для front приложения;
    /opt/repos/worker — для worker приложения. В данных директориях будет проверяться, что файл .gitlab-ci.yml содержит необходимые стадии.
