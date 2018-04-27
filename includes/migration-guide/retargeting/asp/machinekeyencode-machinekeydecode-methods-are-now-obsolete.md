### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Методы MachineKey.Encode и MachineKey.Decode устарели

|   |   |
|---|---|
|Подробные сведения|В настоящее время эти методы считаются устаревшими. При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.|
|Предложение|Взамен рекомендуется использовать <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> и <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версии компилятора. Интерфейсы API по-прежнему поддерживаются.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|

