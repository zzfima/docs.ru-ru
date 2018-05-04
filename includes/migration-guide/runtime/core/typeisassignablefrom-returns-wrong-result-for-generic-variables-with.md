### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom возвращает неверный результат для универсальных переменных с ограничениями

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 <xref:System.Type.IsAssignableFrom(System.Type)> неправильно возвратит <code>false</code> во всех случаях для некоторых универсальных типов с ограничениями.|
|Предложение|Эта проблема была исправлена в обновлении обслуживания. Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии. Кроме того, не используйте IsAssignableFrom с универсальными типами, которые имеют ограничения по универсальным параметрам. В качестве возможного решения воспользуйтесь API отражения.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|Анализаторы|<ul><li>CD0089</li></ul>|

