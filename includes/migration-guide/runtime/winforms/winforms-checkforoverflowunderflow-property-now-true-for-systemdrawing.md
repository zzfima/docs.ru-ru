### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Свойство CheckForOverflowUnderflow WinForm теперь имеет значение true для System.Drawing

|   |   |
|---|---|
|Подробные сведения|Свойство CheckForOverflowUnderflow для сборки System.Drawing.dll имеет значение true.|
|Предложение|Раньше при переполнениях результат усекался без уведомления. Теперь создается исключение <xref:System.OverflowException?displayProperty=name>,|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|

