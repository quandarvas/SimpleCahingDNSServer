Сервер прослушивает 53 порт
Раз в минуту просматривает кеш
Для завершения работы CTRL + C
Сохраняет данные в файл saved_cache.pickle
При старте загружает кеш из этого файла и проверяет ttl

Сервер принимает запрос, забирает пакет, если какая то запись уже есть в кеше она удаляется из запроса, потом запрос передается одному из dns серверов указанных в списке DNS_SERVERS, после того как пришел ответ пакет разбирается и ресурсные записи сохраняются в кеш

В итоге кеш представляет такую структуру name : record_type : (record, end_time), name - доменное имя, record_type - тип ресурсной записи, record - ресурсная запись, end_time - время в секундах когда запись устареет