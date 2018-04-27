### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии

|   |   |
|---|---|
|Подробные сведения|В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.|
|Предложение|Это изменение должно быть прозрачным. Разработчики могут восстановить прежнее поведение, написав следующий код.<pre><code class="language-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|Область|Прозрачный|
|Версия|4.5.1|
|Тип|Среда выполнения|

