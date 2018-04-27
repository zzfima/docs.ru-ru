### <a name="x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>Теперь метод X509Certificate2.ToString(bool) не создает исключение, когда .NET не удается обработать сертификат

|   |   |
|---|---|
|Подробные сведения|Ранее этот метод создавал исключение, если значение <code>true</code> передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework. Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.|
|Предложение|Любой код, зависящий от <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)>, следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

