### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>Начиная с .NET Framework 4.5 GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent возвращают разные значения

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 были усовершенствованы <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> и <xref:System.Windows.Media.FormattedText.Extent> для решения проблем, когда в некоторых случаях в .NET Framework 4.0 прямоугольники были слишком малы для содержащихся глифов. В результате, начиная с .NET Framework 4.5, некоторые ограничивающие прямоугольники будут иметь больший размер, что приведет к незначительным отличиям в макете пользовательского интерфейса.|
|Предложение|Имейте в виду, что размеры некоторых ограничивающих прямоугольников глифов увеличены. Эти изменения обычно улучшают представление и проверку нахождения в поле. Прежнее (до .NET 4.5) поведение можно восстановить, добавив следующую запись в файл app.config.<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|

