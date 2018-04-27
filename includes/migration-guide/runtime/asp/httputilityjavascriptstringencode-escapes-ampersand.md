### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> экранирует символ амперсанда (&amp;).|
|Предложение|Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://msdn.microsoft.com/library/hh975440.aspx) в файле конфигурации.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

