### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>Атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD

|   |   |
|---|---|
|Подробные сведения|При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute?displayProperty=name> экспортируется как <xref:System.ObsoleteAttribute?displayProperty=name> и [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).|
|Предложение|При перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute?displayProperty=name>, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript. Не рекомендуется применять атрибуты <xref:System.ObsoleteAttribute?displayProperty=name> и [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) в коде в управляемых сборках. Это может привести к предупреждениям сборки.|
|Область|Пограничный случай|
|Версия|4.5.1|
|Тип|Изменение целевой платформы|

