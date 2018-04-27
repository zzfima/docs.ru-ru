### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Метод Replace в URL-адресах OData по умолчанию отключен

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен. Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.|
|Предложение|Если необходим метод Replace (который используется редко), его можно включить в параметрах конфигурации (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>). Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|

