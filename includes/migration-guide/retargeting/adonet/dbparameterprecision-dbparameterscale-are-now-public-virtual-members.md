### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision и DbParameter.Scale теперь являются открытыми виртуальными членами

|   |   |
|---|---|
|Подробные сведения|<xref:System.Data.Common.DbParameter.Precision> и <xref:System.Data.Common.DbParameter.Scale> реализованы как открытые виртуальные свойства. Они заменяют соответствующие явные реализации интерфейса: <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> и <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.|
|Предложение|При повторном создании поставщика базы данных ADO.NET эти различия потребуют применения ключевого слова override к свойствам Precision и Scale. Это требуется только в случае повторного создания компонентов; существующие двоичные файлы будут продолжать работать.|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|

