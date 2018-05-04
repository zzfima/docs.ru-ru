### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>SQL-подключения не в составе пула приводят к утечке памяти, если их явно не удалить

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 SQL-подключения вне пула, которые не предоставляются явно (с помощью Dispose, Close или использования), приводят к утечке памяти|
|Предложение|Эта проблема исправлена в сервисном обновлении .NET Framework 4.5. Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии. Кроме того, этой проблемы можно избежать с помощью <xref:System.Data.SqlClient.SqlConnection?displayProperty=name> в шаблоне использования (рекомендованный метод) или путем явного вызова Dispose или Close, когда соединение больше не нужно.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

