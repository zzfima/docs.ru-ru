### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Изменение поведения API-интерфейсов языка описания данных (DDL)

|   |   |
|---|---|
|Подробные сведения|Поведение API-интерфейсов языка DDL при заданном значении AttachDBFilename изменилось следующим образом.<ul><li>В строках подключения не требуется указывать значение Initial Catalog. Ранее требовались оба значения — AttachDBFilename и Initial Catalog.</li><li>Если указаны AttachDBFilename и Initial Catalog и данный MDF-файл существует, метод ObjectContext.DatabaseExists возвращает значение true. Раньше он возвращал значение false.</li><li>Если указаны AttachDBFilename и Initial Catalog и данный MDF-файл существует, вызов метода ObjectContext.DeleteDatabase приведет к удалению файлов.</li><li>Если метод ObjectContext.DeleteDatabase вызывается в случае, когда в строке подключения указывается значение AttachDBFilename с несуществующим MDF-файлом и несуществующим Initial Catalog, метод вызывает исключение InvalidOperationException. Раньше он вызывал исключение SqlException.</li></ul>|
|Предложение|Эти изменения облегчают создание средств и приложений, в которых используются API-интерфейсы DDL. Эти изменения могут повлиять на совместимость приложений в следующих сценариях:<ul><li>Пользователь пишет код, который выполняет команду DROP DATABASE напрямую, а не вызывает ObjectContext.DeleteDatabase, если ObjectContext.DatabaseExists возвращает значение true. Это нарушает логику существующего кода, если база данных не присоединена, но MDF-файл существует.</li><li>Пользователь пишет код, который ожидает, что метод ObjectContext.DeleteDatabase вызовет исключение SqlException, а не исключение InvalidOperationException, когда Initial Catalog и MDF-файл не существуют.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|

