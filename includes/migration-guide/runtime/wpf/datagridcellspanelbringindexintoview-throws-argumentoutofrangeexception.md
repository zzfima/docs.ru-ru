### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException

|   |   |
|---|---|
|Подробные сведения|Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.  Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=name>.|
|Предложение|Выполните одно из следующих действий:<ol><li>Выполнить обновление до .NET 4.7.</li><li>Установить новейшее служебное исправление для .NET 4.6.2.</li><li>Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|

