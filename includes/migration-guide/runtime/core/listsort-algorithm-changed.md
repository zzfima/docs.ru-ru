### <a name="listsort-algorithm-changed"></a>Изменен алгоритм List.Sort

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5, алгоритм сортировки <xref:System.Collections.Generic.List%601?displayProperty=name> был изменен и реализует интроспективную сортировку вместо быстрой. Сортировка <xref:System.Collections.Generic.List%601?displayProperty=name> никогда не была стабильной, однако это изменение может привести к потере стабильности при сортировке в различных других сценариях. Это означает, что эквивалентные элементы могут сортироваться в разном порядке при последовательных вызовах API.|
|Предложение|Поскольку старый алгоритм сортировки также был нестабилен (в несколько другом плане), не следует использовать код, который зависит от постоянства порядка сортировки эквивалентных элементов. Если в коде присутствовала такая зависимость и он ранее выполнялся без ошибок, его следует обновить для использования компаратора, который будет осуществлять детерминированную сортировку элементов в необходимом порядке.|
|Область|Прозрачный|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|

