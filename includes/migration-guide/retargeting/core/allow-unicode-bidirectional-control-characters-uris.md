### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Разрешить двунаправленные управляющие символы Юникода в URI

|   |   |
|---|---|
|Подробные сведения|Юникод определяет несколько специальных управляющих символов, используемых для указания ориентации текста. В предыдущих версиях платформы .NET Framework эти символы ошибочно удалялись из всех URI, даже если были представлены в процентной кодировке. В целях соблюдения стандарта [RFC 3987](http://tools.ietf.org/html/rfc3987) теперь мы разрешаем эти символы в URI. При обнаружении незакодированных символов в URI выполняется процентное кодирование. Символы в процентной кодировке остаются без изменений.|
|Предложение|Для приложений, предназначенных для версий .NET Framework начиная с 4.7.2, поддержка двунаправленных символов Юникода включена по умолчанию. Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, поддержка двунаправленных символов Юникода отключена по умолчанию. Вы можете включить это изменение, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

