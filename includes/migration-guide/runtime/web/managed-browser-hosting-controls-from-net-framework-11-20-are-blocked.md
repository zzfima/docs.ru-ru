### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Элементы управления Managed Browser в .NET Framework 1.1 и 2.0 заблокированы

|   |   |
|---|---|
|Подробные сведения|Размещение этих элементов управления в Internet Explorer блокируется.|
|Предложение|Internet Explorer не сможет запустить приложение, в котором используются управляемые элементы управления, размещенные в браузере. Прежнее поведение можно восстановить путем установки параметру EnableIEHosting подраздела реестра <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> значения <code>1</code> для систем x86 и для 32-разрядных процессов в системах x64, а также путем установки параметру <code>EnableIEHosting</code> подраздела реестра <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> значения <code>1</code> для 64-разрядных процессов в системах x64.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|

