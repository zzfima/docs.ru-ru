### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>Непредвиденное исключение InvalidCastException в результате действия InvokeMethod в WF4

|   |   |
|---|---|
|Подробные сведения|При использовании <xref:System.Activities.Statements.InvokeMethod>, нацеленного на метод с параметром, допускающим значение NULL, может возникнуть исключение <xref:System.InvalidCastException?displayProperty=name>.|
|Предложение|Это поведение было восстановлено в сервисном обновлении .NET Framework 4.5. Чтобы устранить эту проблему, обновите .NET Framework 4.5 (или выполните обновление до .NET Framework 4.5.1 или более поздней версии).|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|Анализаторы|<ul><li>CD0088</li></ul>|

