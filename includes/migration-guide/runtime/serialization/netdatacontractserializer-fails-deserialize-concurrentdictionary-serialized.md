### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer не удается выполнить десериализацию ConcurrentDictionary, сериализованного с использованием другой версии .NET

|   |   |
|---|---|
|Подробные сведения|По своей структуре <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> может использоваться только при использовании одних и тех же типов CLR на концах сериализации. Таким образом, не гарантируется, что объект, сериализованный в одной версии .NET Framework, может быть десериализован в другой версии платформы.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> некорректно десериализуется в .NET Framework 4.5.1 или более поздней версии, если сериализация этого типа была выполнена в .NET Framework 4.5 или предшествующих версий.|
|Предложение|Эту проблему можно обойти несколькими способами:<ul><li>Обновите компьютер, на котором выполняется сериализация, до версии .NET Framework 4.5.1.</li><li>Используйте <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> вместо <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>, поскольку он не требует, чтобы на сторонах сериализации и десериализации использовались одинаковые типы CLR .</li><li>Используйте <xref:System.Collections.Generic.Dictionary%602?displayProperty=name> вместо <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>, поскольку в нем не наблюдается это нарушение совместимости между версиями 4.5-&gt;4.5.1.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|

