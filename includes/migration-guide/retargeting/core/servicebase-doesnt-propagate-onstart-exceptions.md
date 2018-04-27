### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase не распространяет исключения OnStart

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7 и более ранних версий исключения, возникшие при запуске службы, не распространяются на вызывающий код <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>. Начиная с приложений, ориентированных на .NET Framework 4.7.1, среда выполнения распространяет исключения в <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> для служб, которые не удается запустить.|
|Предложение|Если при запуске службы есть исключение, оно будет распространяться. Это поможет диагностировать случаи, когда происходит сбой запуска служб. Если такое поведение нежелательно, то его можно отключить, добавив следующий элемент <AppContextSwitchOverrides> в раздел <runtime> файла конфигурации приложения:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Если приложение предназначено для версии до 4.7.1, но вы хотите использовать это поведение, добавьте следующий элемент <AppContextSwitchOverrides> в раздел <runtime> файла конфигурации приложения:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

