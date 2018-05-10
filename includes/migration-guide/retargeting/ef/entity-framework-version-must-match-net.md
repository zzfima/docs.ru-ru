### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Версия Entity Framework должна соответствовать версии .NET Framework

|   |   |
|---|---|
|Подробные сведения|Версия Entity Framework должна соответствовать версии платформы .NET Framework. Для .NET Framework 4.5 рекомендуется Entity Framework 5. Существуют некоторые известные проблемы с EF 4.x в проекте .NET Framework 4.5, связанные с <xref:System.ComponentModel.DataAnnotations>. В .NET 4.5 они были перемещены в другую сборку, поэтому существуют проблемы с выбором заметок для использования.|
|Предложение|Обновление до версии Entity Framework 5 для .NET Framework 4.5|
|Область|Значительно|
|Версия|4.5|
|Тип|Изменение целевой платформы|

