### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode и WebUtility.HtmlDecode корректно совершают круговой путь в BMP

|   |   |
|---|---|
|Подробные сведения|Для приложений, предназначенных для .NET Framework 4.5, символы, не входящие в базовый многоязыковый набор кодировок (BMP), правильно передаются в оба конца, если они передаются методам <xref:System.Net.WebUtility.HtmlDecode(System.String)>.|
|Предложение|Это изменение не должно влиять на текущие приложения, но для восстановления исходного поведения задайте атрибут <code>targetFramework</code> элемента <code>&lt;httpRuntime&gt;</code> для строки, отличный от &quot;4.5&quot;. Также можно задать атрибуты <code>unicodeEncodingConformance</code> и <code>unicodeDecodingConformance</code> элемента конфигурации <code>&lt;webUtility&gt;</code>, чтобы контролировать это поведение вне зависимости от целевой версии .NET Framework.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|

