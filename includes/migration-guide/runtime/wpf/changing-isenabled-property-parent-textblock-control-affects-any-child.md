### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Изменение свойства IsEnabled для родительского объекта элемента управления TextBlock влияет на любые дочерние элементы управления

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.6.2, изменение свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> родительского объекта элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=name> влияет на любые дочерние элементы управления (например, гиперссылки и кнопки) элемента <xref:System.Windows.Controls.TextBlock?displayProperty=name>. В .NET Framework 4.6.1 и более ранних версий элементы управления внутри элемента <xref:System.Windows.Controls.TextBlock?displayProperty=name> не всегда отражали состояние свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> родительского объекта <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Предложение|Отсутствует. Это изменение соответствует ожидаемому поведению для элементов управления, содержащихся внутри элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Область|Дополнительный номер|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

