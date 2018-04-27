### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>Метод WebUtility.HtmlDecode больше не декодирует недопустимую входную последовательность

|   |   |
|---|---|
|Подробные сведения|По умолчанию методы декодирования больше не декодируют недопустимую входную последовательность в недопустимую строку UTF-16. Вместо этого они возвращают исходные входные данные.|
|Предложение|Изменение в выходных данных декодера может иметь значение, только если в строках хранятся двоичные данные, а не данные UTF-16. Чтобы явно контролировать это поведение, присвойте атрибуту <code>aspnet:AllowRelaxedUnicodeDecoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) значение <code>true</code>, чтобы разрешить устаревшее поведение, или значение <code>false</code>, чтобы разрешить текущее поведение.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|

