### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>Метод System.Threading.Tasks.Task больше не создает исключение ObjectDisposedException после удаления объекта

|   |   |
|---|---|
|Подробные сведения|За исключением <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> методы <xref:System.Threading.Tasks.Task?displayProperty=name> больше не вызывают исключение <xref:System.ObjectDisposedException?displayProperty=name> после удаления объекта. Это изменение поддерживает использование кэшированных задач. Например, метод может возвратить кэшированную задачу для представления уже выполненной операции вместо выделения новой задачи. В предыдущих версиях платформы .NET Framework это было невозможно, поскольку любой потребитель задачи мог удалить ее, что делало ее непригодной для использования.|
|Предложение|Имейте в виду, что методы Task больше не могут создавать исключения <xref:System.ObjectDisposedException?displayProperty=name> при удалении объекта. Если приложение зависело от этого исключения, чтобы знать, что задача была удалена, его необходимо обновить, чтобы явно проверять состояние задачи с помощью <xref:System.Threading.Tasks.Task.Status>.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|

