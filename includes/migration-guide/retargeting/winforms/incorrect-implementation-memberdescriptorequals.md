### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Неправильная реализация MemberDescriptor.Equals

|   |   |
|---|---|
|Подробные сведения|Исходная реализация метода &quot;Equals&quot; сравнивала два разных свойства строки из объектов для сравнения по категории со строкой описания. После исправления метод сравнивает &quot;категорию&quot; первого объекта с &quot;категорией&quot; второго и &quot;описание&quot; с &quot;описанием&quot;. Для значения конфигурации MemberDescriptorEqualsReturnsFalseIfEquivalent можно задать значение true, чтобы отказаться от нового поведения при ориентации на версию 4.6.2, или значение false, чтобы включить это исправление при ориентации на версию платформы до 4.6.2.|
|Предложение|Если приложение зависит от того, что MemberDescriptor.Equals иногда возвращает значение false, когда дескрипторы эквивалентны, и вы используете .NET Framework 4.6.2, у вас есть несколько вариантов:<ol><li>Внесите в код изменения для сравнения полей &quot;категории&quot; и &quot;описания&quot; вручную в дополнение к методу Equals.</li><li>Откажитесь от этого изменения, добавив следующее значение в файл app.config:</li></ol><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Если ваше приложение предназначено для .NET Framework 4.6.1 или более ранней версии и вы хотите включить это изменение, вы можете настроить переключение совместимости на значение false, добавив следующее значение в файл app.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|

