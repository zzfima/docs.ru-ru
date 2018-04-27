### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>). При попытке сериализации каталога MEF происходит вызов исключения.|
|Предложение|Больше не следует использовать MEF для создания сериализатора.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|

