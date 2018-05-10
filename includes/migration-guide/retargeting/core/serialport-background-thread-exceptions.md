### <a name="serialport-background-thread-exceptions"></a>Исключения фонового потока SerialPort

|   |   |
|---|---|
|Подробные сведения|Фоновые потоки, созданные с помощью потоков <xref:System.IO.Ports.SerialPort>, больше не завершают процесс при возникновении исключений ОС. <br/>В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, процесс завершался при возникновении исключений операционной системы в фоновом потоке, созданном с помощью потока <xref:System.IO.Ports.SerialPort>. <br/>В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, фоновые потоки ожидают события ОС, связанные с активным последовательным портом, и могут аварийно завершиться в некоторых случаях, например при внезапном удалении последовательного порта.|
|Предложение|Для приложений, предназначенных для .NET Framework 4.7.1, можно отказаться от обработки исключений, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.1 или более поздней версии, можно включить обработку исключений, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|

