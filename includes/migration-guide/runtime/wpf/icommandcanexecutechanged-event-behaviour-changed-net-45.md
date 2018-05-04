### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>В .NET 4.5 изменено поведение события ICommand.CanExecuteChanged

|   |   |
|---|---|
|Подробные сведения|В платформе .NET Framework 4.5 событие <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> игнорировалось, кроме случаев, когда отправителем события был тот же объект, который создал событие. Эта ошибка была исправлена в обслуживающих обновлениях .NET Framework 4.5.|
|Предложение|Эта ошибка была исправлена в обслуживающих выпусках .NET Framework 4.5, поэтому ее можно избежать, убедившись, что платформа .NET Framework не требует обновления, или выполнив обновление до .NET Framework 4.5.1. Кроме того, код приложения, использующий <xref:System.Windows.Input.ICommand?displayProperty=name>, можно изменить, чтобы отправитель, вызывающий команду <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name>, совпадал с объектом, создающим событие.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|Анализаторы|<ul><li>CD0084</li></ul>|

