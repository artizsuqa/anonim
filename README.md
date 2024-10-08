# Анонимный чат бот
-----

Создали: @ArtizSQ, @RegaaTG

### 🔰 Описание
-----
Чат-бот для анонимной отправки сообщений. Построен на базе `aiogram`, `sqlalchemy`.

Данные пользователя находятся в файле **`db.sqlite3`**, который создается после запуска бота. (В файлах этого проекта его нет, дабы избежать возможной утечки данных). В базе хранится только **4 столбца с данными** (ID, количество полученных и отправленных сообщений, секретный код для отправки сообщений). В БД (база данных) нет никакой информации об: Username, имени, фамилии и пр.

Гарантированная анонимность, отправителя невозможно узнать, поскольку никакой информации не сохраняется. 

Версия бота: `v-beta`

### ⭐️ Возможности
-----
- Отправка сообщений по типу:
  - Текст
  - Фото
  - Видео
  - Голосовое сообщение
  - Кружок
  - Файл
  - Музыка
  - Стикеры
  - GIF
  

- Полная анонимность отправителя и получателя (код генерирует 10 случайных байтов и преобразует их в шестнадцатеричное представление. Подробнее в [Анонимность в боте](#-анонимность-в-боте))


### 👀 Анонимность в боте
-----
У каждого пользователя есть свой уникальных код, благодаря которому ID получателя неизвестен.

Этот код генерирует 10 случайных байтов и преобразует их в шестнадцатеричное представление. Давайте разберемся по шагам:

1. `os.urandom(10)`:
   - `os.urandom` - функция из модуля `os`, которая генерирует криптографически безопасные случайные байты.
   - `10` - количество байтов, которые нужно сгенерировать.
   - Результат - это строка байтов, например, `b'\x03\x1d\xa2\x9c\x05\xe9\x00\x91\xd3\x81'`.

2. `.hex()`:
   - `.hex()` - метод, который преобразует строку байтов в шестнадцатеричное представление.
   - Результат - строка, содержащая шестнадцатеричные символы, например, `'031da29c05e90091d381'`.

Зачем использовать этот код:

- Генерация случайных идентификаторов: Шестнадцатеричный код часто используется для генерации уникальных идентификаторов, например, для сессий, токенов или элементов базы данных.
- Криптография: Криптографически безопасные случайные данные необходимы для создания ключей шифрования, солей и других элементов криптографических систем.



### 💻 Для разработчиков
-----
Вы можете добавлять новые функции и отправлять одному из разработчиков. Если ваша идея подойдет под бота, мы добавим ее. (По желанию укажем ваши данные в разработчиках бота)
