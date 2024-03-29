# movies-explorer-api

Приложение Movies Explorer (дипломный проект Я.Практикума): бэкенд-часть с API-сервером

# Movies Explorer (бэкенд-часть)

Репозиторий для бэкенд-части приложения с API-сервером

## Доступ к рабочему серверу
Ссылка на сайт: http://api.movies-lugvictoria.nomoredomains.work/



``` bash

```
*Доступ к серверу может быть получен только для владельца репозитория и команды Практикума*

## Приложение Movies Explorer

Приложение Movies Explorer - сервис, в котором можно найти фильмы по запросу и сохранить в личном кабинете.

Это дипломный проект Яндекс.Практикума по специальности "Веб-разработчик".

### Структура приложения 
Приложение состоит из двух частей:
1. Movies Explorer (бэкенд-часть) ⬅ *этот репозиторий*
2. [Movies Explorer (фронтенд-часть)](                                )


## API
### Регистрация пользователя
`POST /signup` - создаёт пользователя с переданными в теле email, password и name

### Аутентификация
`POST /signin` - проверяет введенные почту и пароль и возвращает обратно JWT-токен

### Информация о пользователе
`GET /users/me` - возвращает данные о пользователе (email и имя)  
`PATCH /users/me` - обновляет данные о пользователе (email и имя)

### Фильмы
`GET /movies` - возвращает список выделенных и сохраненных пользователем фильмов 
`POST /movies` - создаёт фильм с введенной информацией в полях данных : country, director, duration, year, description, image, trailer, nameRU, nameEN и thumbnail, movieId  
`DELETE /movies/_id` - удаляет сохранённый фильм по идентификатору id  

### Защита роутов авторизацией
Доступ к роутам `/users` и `/movies` будет получен с введенным JWT-токеном. Токен должен содержаться в каждом запросе к защищенным роутам:
- заголовок `Authorization`
- значение вида `Bearer eyJh...Xbhc`

## Функциональность
- работа с базой данной приложения через роуты
- регистрация и аутентификация пользователя
- часть роутов защищена авторизацией через JWT-токен
- валидация данных в запросе до передачи контроллеру и перед записью в базу данных
- сбор логов сервера в формате JSON (запросы и ошибки)
- централизованный обработчик ошибок
- хранение пароля пользователя в виде хэша с солью
- поддержка работы с доступом по https
- безопасное хранение на сервере ключа для генерации JWT-токенов
- обеспечение безопасности заголовков запросов
- конфигурация и константы приложения в отдельных файлах
- ограничение числа запросов с одного IP

## Стек технологий
- сервер на `Ubuntu` в Яндекс.Облаке
- ssh-ключи для доступа к серверу
- API-сервер на `Node.js` + `express.js`
- база данных на `MongoDB` + `Mongoose`
- обновление кода на сервере через `Git`
- менеджер процессов на сервере `pm2`
- раздача фронтенда через `nginx`
- обратный прокси-сервер на `nginx`
- файрвол `ufw`
- SSL-сертификаты от `Letsencrypt`

## Статус разработки
⚒️ *В процессе*
