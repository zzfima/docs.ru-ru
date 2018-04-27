### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>Теперь WF сериализует Expressions.Literal&lt;T&gt; DateTimes по-другому (нарушает работу пользовательских средств синтаксического анализа XAML)

|   |   |
|---|---|
|Подробные сведения|Связанный объект <xref:System.Windows.Markup.ValueSerializer> преобразует объект <xref:System.DateTime?displayProperty=name> или <xref:System.DateTimeOffset?displayProperty=name>, компоненты Second и <xref:System.DateTime.Millisecond?displayProperty=name> которого не равны нулю и (для значения <xref:System.DateTime?displayProperty=name>) свойство <xref:System.DateTime.Kind> которого не равно Unspecified, в синтаксис элемента свойства вместо строки. Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=name> и <xref:System.DateTimeOffset?displayProperty=name> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|
|Предложение|Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=name> и <xref:System.DateTimeOffset?displayProperty=name> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|

