# mvp messenger
Course:
https://github.com/moguchev/microservices_like_in_bigtech_5

## Design overview

<p align="center">
  <img alt="Temporary schema" src="./architecture/images/diag.svg"/>
</p>



api_gateway:
    http

auth_service:
    grpc

chat_service:

subscriber_service:

user_service:




TODO:
Регистрация пользователя (по почте и паролю + Oauth)
Вход/авторизация (по почте и паролю + Oauth)

Редактирование профиля пользователя (никнейм - уникальный, информация о себе, аватарка)

Поиск пользователей по никнейму
Добавить пользователя в друзья
Убрать пользователя из друзей
Подтвердить или отклонить запрос на дружбу
Просмотр списка своих друзей (подтвердивших и не подтвердивших еще)
Написать сообщение другу
Получить сообщение из чата с пользователем


#1
Описать, за что будет отвечать каждый сервис, какие данные будет у себя хранить, с какими сервисами взаимодействовать, какие методы/API будет предоставлять, какие события публиковать/потреблять.

Нарисовать архитетуру (блок схему) backend приложения со связми сервисов (кто куда ходит и за чем).

⭐ Для каждого сервиса выбрать конкретную БД и обосновать, почему выбрана именно она. Если сервисы общаются асинхронно с помощью брокера сообщений, выбрать конкретный и обосновать.


Написать инструкцию или скрипт для того, чтобы можно было поднять все сервисы в контейнерах локально. (Подсказка: для удобства локальной разработки лучше всего воспользоваться docker-compose и Makefile)

⭐ Реализовать стратегии деплоя blue-green и canary с помощью стандартных средств kubernetes.



#2
Для каждого сервиса из  подход API (gRPC, REST) и аргументировать почему выбрали его

Описать для каждого сервиса в Swagger/Protobuf schema ваш API

Реализовать сервер обслуживающий API (REST/gRPC server). Обработка входящих запросов, валидация запросов (без бизнес логики) и отдача заглушки в виде ответа.

⭐ Создать REST/JSON-RPC/GraphQL/gRPC клиентов (интегрировать общение сервисов между собой)

Добавить grpc-gateway и генерацию OpenAPI

⭐ Добавить linter и форматирование proto файлов

⭐ Прикрутить в сервисе с grpc-gateway SwaggerUI сервер, с помощью которого можно выполнять запросы на grpc-gateway proxy.