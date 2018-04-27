### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Некоторые интерфейсы API .NET создают первый экземпляр (обрабатываемый) EntryPointNotFoundExceptions

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 несколько методов .NET начали создавать первый экземпляр <xref:System.EntryPointNotFoundException?displayProperty=name>. Эти исключения обрабатывались в .NET Framework, но могли нарушать работу службы автоматизации тестирования, которая не ожидала первых экземпляров исключений. Те же интерфейсы API препятствуют работе некоторых сценариев ApiVerifier, если включен тест HighVersionLie.|
|Предложение|Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, службу автоматизации тестирования можно обновить, чтобы она не прерывала свое выполнение при создании первого экземпляра <xref:System.EntryPointNotFoundException?displayProperty=name>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|

