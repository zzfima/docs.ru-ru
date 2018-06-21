### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Трассировки стека, полученные при использовании переносимых PDB-файлов, теперь включают сведения об исходном файле и строке по запросу

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.7.2 трассировки стека, полученные при использовании переносимых PDB-файлов, включают сведения об исходном файле и строке по запросу. В версиях до .NET Framework 4.7.2 сведения об исходном файле и строке были недоступны при использовании переносимых PDB-файлов, даже по явному запросу.|
|Предложение|Для приложений, предназначенных для .NET Framework 4.7.2, можно отказаться от вывода сведений об исходном файле и строке при использовании переносимых PDB-файлов, если это нежелательно, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.2 или более поздней версии, можно включить вывод сведений об исходном файле и строке при использовании переносимых PDB-файлов, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)?displayProperty=nameWithType><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)?displayProperty=nameWithType></li></ul>|

