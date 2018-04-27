### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek может возвращать ошибочные значения NULL в выходном параметре

|   |   |
|---|---|
|Подробные сведения|В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).|
|Предложение|Эта проблема решена в EntityFramework 4.5.1. Чтобы устранить проблему, выполните обновление до этой версии платформы.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

