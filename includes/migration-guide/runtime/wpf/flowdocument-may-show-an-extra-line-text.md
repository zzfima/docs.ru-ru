### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument может отображать дополнительную строку текста

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях при работе с .NET Framework 4.5 в элементе <xref:System.Windows.Documents.FlowDocument> отображается лишняя строка текста по сравнению с выполнением в .NET Framework 4.0. Случаи неправильного или неразборчивого отображения текста в связи с этим изменением не выявлены, однако эта проблема может привести к отображению текста, который ранее был опущен из представления <xref:System.Windows.Documents.FlowDocument>.|
|Предложение|В некоторых случаях для восстановления исходного количества строк можно уменьшить значение свойства PageHeight на единицу.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|

