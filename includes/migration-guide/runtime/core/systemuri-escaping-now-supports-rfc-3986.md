### <a name="systemuri-escaping-now-supports-rfc-3986"></a>Экранирование System.Uri теперь поддерживает RFC 3986

|   |   |
|---|---|
|Подробные сведения|Экранирование URI изменилось в .NET Framework 4.5 для поддержки [RFC 3986](http://tools.ietf.org/html/rfc3986). Внесены следующие конкретные изменения.<ul><li>Метод <xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.</li><li>Метод <xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> не преобразует в escape-последовательность зарезервированные символы.</li><li>Метод <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> не создает исключение, если ему встречается неверная escape-последовательность.</li><li>Преобразование незарезервированных символов в escape-символы отменяется.</li></ul>|
|Предложение|<ul><li>Обновления приложений не зависят от <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> для создания исключения в случае недопустимой escape-последовательности. Такие последовательности должны обнаруживаться сразу же.</li><li>Аналогичным образом ожидается, что экранированные и неэкранированные URI и строки данных могут отличаться в .NET Framework 4.0 и .NET Framework 4.5 и их не следует сравнивать в версиях .NET напрямую. Их необходимо проанализировать и нормализовать в одной версии .NET перед выполнением каких-либо сравнений.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|

