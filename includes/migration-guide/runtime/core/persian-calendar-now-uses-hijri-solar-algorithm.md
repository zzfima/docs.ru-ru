### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Теперь в персидском календаре используется алгоритм солнечного календаря хиджры

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.6 класс <xref:System.Globalization.PersianCalendar?displayProperty=name> использует алгоритм солнечного календаря хиджры. Начиная с .NET Framework 4.6 при преобразовании дат между <xref:System.Globalization.PersianCalendar?displayProperty=name> и другими календарями может быть получен немного другой результат для дат, ранее 1800 г. или позднее 2023 г. (по григорианскому календарю). Кроме того, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> теперь <code>March 22, 0622 instead of March 21, 0622</code>.|
|Предложение|Имейте в виду, что при использовании персидского календаря в .NET 4.6 некоторые даты в прошлом или будущем могут несколько отличаться. Кроме того, даты, сериализуемые между процессами, которые могут выполняться в различных версиях .NET Framework, не следует хранить в виде строк дат персидского календаря (поскольку эти значения могут быть разными).|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|

