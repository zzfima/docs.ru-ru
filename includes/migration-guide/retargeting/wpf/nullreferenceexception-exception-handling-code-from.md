### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException в коде обработки исключений из ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Подробные сведения|Ошибка в коде обработки исключений для <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> вызывала некорректное исключение <xref:System.NullReferenceException?displayProperty=name> вместо предполагаемого исключения (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> или <xref:System.IO.FileNotFoundException?displayProperty=name>). Это изменение устраняет эту ошибку. Теперь метод вызывает правильное исключение. По умолчанию все приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, будут и далее вызывать исключение <xref:System.NullReferenceException?displayProperty=name> в целях совместимости. В приложениях, предназначенных для .NET Framework 4.7 и более поздних версий, будут возникать правильные исключения.|
|Предложение|Разработчики, желающие по-прежнему получать <xref:System.NullReferenceException?displayProperty=name> при работе с .NET Framework 4.7 и более поздних версий, могут добавить следующее в файл App.config приложения:<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|

