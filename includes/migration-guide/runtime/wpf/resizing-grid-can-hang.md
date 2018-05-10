### <a name="resizing-a-grid-can-hang"></a>Изменение размеров сетки может привести к зависанию

|   |   |
|---|---|
|Подробные сведения|При изменении макета <code>T:System.Windows.Controls.Grid</code> в следующих обстоятельствах может возникать бесконечный цикл:<ul><li>Определения строк содержат два атрибута *-rows, которые объявляют значения MinHeight и MaxHeight.</li><li>Содержимое *-rows не превышает ограничение, устанавливаемое соответствующим значением MaxHeight.</li><li>Первое значение MinHeight (плюс любые другие фиксированные или автоматические строки) превышает доступную высоту сетки.</li><li>Приложение предназначено для .NET Framework 4.7 или использует алгоритм выделения версии 4.7, включенный с помощью параметра <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</li></ul>Кроме того, цикл может возникать при наличии более двух строк или в аналогичных случаях для столбцов. Проблема устранена в .NET Framework 4.7.1.|
|Предложение|Выполните обновление до .NET Framework 4.7.1.  Кроме того, если вам не требуется алгоритм выделения версии 4.7, вы можете использовать следующий параметр конфигурации:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Среда выполнения|

