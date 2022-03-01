## Тестовое задание: Рефакторинг небольшого приложения на Go

### Что было добавлено:
* Функции getData & setData
> В коде большое количество однотипных вызовов ioutill.ReadFile &  ioutill.WriteFile, результат которых обрабатываеся пакетом json
* Проверка существования файла
>  При запуске приложения необходимо убедиться, что файл(база данных) доступна
* sync.RWMutex
> Файл с данными не потокобезопасен
* ErrResponse в хендлере getUser
> Если пользователя по указанному id не существует, ответом будет ошибка. Как и в случае с deleteUser

### Что можно изменить:
* Так как подразумевается увеличение количества сущностей и функций - можно использовать **чистую архитектуру** для удобства дальнейшей разработки. Хотя бы слои хендлеров и сущностей. Это также поможет в тестировании кода. 
* Сделать полноценную обработку ошибок.
