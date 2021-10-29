
## Салимов Наиль 11-802

### Задание 2


Ссылка на Задание 1: https://github.com/Nail-Salimov/CloudTechnology


Для нахождения лиц используется сервис Face++.   Фотографии лиц хранятся по пути 'название_альбома/имя_исходного_файла/фото_лица'


#### Облачная функция

Код облочной функции лежит в в файле index.py. Для работы, нужно добавить следующие переменные окружения:

- FACE_SECRET_KEY (секретный ключ от анализотора фото Face++)
- FACE_ACCESS_KEY (ключ доступа от анализотора фото Face++)
- S3_SECRET_KEY   (секретный ключ от аккаунта Yandex Cloud, где находится Object Storage)
- S3_ACCESS_KEY   (ключ доступа от аккаунта Yandex Cloud, где находится Object Storage)
- SQS_SECRET_KEY  (секретный ключ от аккаунта Yandex Cloud, где находится Message Queue)
- SQS_ACCESS_KEY  (ключ доступа от аккаунта Yandex Cloud, где находится Message Queue)
- SQS_QUEUE       (Имя очереди)

Точка входа: index.handler .

Также добавить в облачную функцию файл: requirements.txt . 

#### Хранилище

Хранилище должно публичным для:

- Доступа на чтение объектов
- Доступа к списку объектов

Доступ на чтение настроек: ограниченный. 

Класс хранилища: стандартный. 


#### Триггер

- Тип: Object Storage.
- Запускаемый ресурс: Функция
- Бакет: (имя хранилища)
- Тип события: создание
- Функция: (имя функции)
- Сервисный аккаунт: (свой сервисный аккаунт)

#### Очередь

- Имя: (имя, которое будет указано в SQS_QUEUE)
- Тип: Стандартная